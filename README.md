import os, zipfile

root = "/mnt/data/GabaaOromoo"
zip_path = "/mnt/data/GabaaOromoo_full_project.zip"

cloud_data = {
# Render Cloud Blueprint for automatic server & database deployment
"render.yaml": """services:
  - type: web
    name: gabaaoromoo-backend
    env: node
    plan: free
    rootDir: server
    buildCommand: npm install && npx prisma generate
    startCommand: npm run start
    envVars:
      - key: NODE_ENV
        value: production
      - key: PORT
        value: 4000
      - key: DATABASE_URL
        fromDatabase:
          name: gabaaoromoo-db
          property: connectionString

databases:
  - name: gabaaoromoo-db
    plan: free
""",

# GitHub Actions workflow to build your Android APK automatically in the cloud
".github/workflows/android-build.yml": """name: Build GabaaOromoo Android App
on:
  push:
    branches: [ main, master ]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Source Code
        uses: actions/checkout@v4

      - name: Setup Node.js
        uses: actions/setup-node@v4
        with:
          node-version: 20
          cache: 'npm'

      - name: Install Frontend Dependencies
        run: |
          npm install
          npm run copy

      - name: Set up JDK 17
        uses: actions/setup-java@v4
        with:
          distribution: 'zulu'
          java-version: '17'

      - name: Setup Android Project Layout
        run: |
          npx cap add android || true
          npx cap sync android

      - name: Build Android APK (Release)
        run: |
          cd android
          ./gradlew assembleRelease

      - name: Upload Finished APK Artifact
        uses: actions/upload-artifact@v4
        with:
          name: GabaaOromoo-Release-APK
          path: android/app/build/outputs/apk/release/app-release-unsigned.apk
"""
}

# Inject the deployment pipelines into the project structure
for rel, content in cloud_data.items():
    p = os.path.join(root, rel)
    os.makedirs(os.path.dirname(p), exist_ok=True)
    with open(p, "w", encoding="utf-8") as f:
        f.write(content)

# Re-pack everything tightly
if os.path.exists(zip_path):
    os.remove(zip_path)
with zipfile.ZipFile(zip_path, "w", zipfile.ZIP_DEFLATED) as z:
    for base, _, names in os.walk(root):
        for name in names:
            full = os.path.join(base, name)
            z.write(full, os.path.relpath(full, "/mnt/data"))

print("CLOUD_PIPELINE_INJECTED_SUCCESSFULLY")
GabaaOromoo/
├── www/
├── server/
├── package.json
├── capacitor.config.json
└── .gitignore
