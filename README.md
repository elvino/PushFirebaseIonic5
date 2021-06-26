# PushFirebaseIonic5
Push Notification com Ionic 5 e Firebase
These are Cordova resources. You can replace icon.png and splash.png and run

 ionic cordova resources to generate custom icons and splash screens for your app. 
 See ionic cordova resources --help for details.

Cordova reference documentation:

Icons: https://cordova.apache.org/docs/en/latest/config_ref/images.html
Splash Screens: https://cordova.apache.org/docs/en/latest/reference/cordova-plugin-splashscreen/

{
  "$schema": "./node_modules/@angular/cli/lib/config/schema.json",
  "version": 1,
  "defaultProject": "app",
  "newProjectRoot": "projects",
  "projects": {
    "app": {
      "root": "",
      "sourceRoot": "src",
      "projectType": "application",
      "prefix": "app",
      "schematics": {},
      "architect": {
        "build": {
          "builder": "@angular-devkit/build-angular:browser",
          "options": {
            "outputPath": "www",
            "index": "src/index.html",
            "main": "src/main.ts",
            "polyfills": "src/polyfills.ts",
            "tsConfig": "tsconfig.app.json",
            "assets": [
              {
                "glob": "**/*",
                "input": "src/assets",
                "output": "assets"
              },
              {
                "glob": "**/*.svg",
                "input": "node_modules/ionicons/dist/ionicons/svg",
                "output": "./svg"
              }
            ],
            "styles": [
              {
                "input": "src/theme/variables.scss"
              },
              {
                "input": "src/global.scss"
              }
            ],
            "scripts": []
          },
          "configurations": {
            "production": {
              "fileReplacements": [
                {
                  "replace": "src/environments/environment.ts",
                  "with": "src/environments/environment.prod.ts"
                }
              ],
              "optimization": true,
              "outputHashing": "all",
              "sourceMap": false,
              "extractCss": true,
              "namedChunks": false,
              "aot": true,
              "extractLicenses": true,
              "vendorChunk": false,
              "buildOptimizer": true,
              "budgets": [
                {
                  "type": "initial",
                  "maximumWarning": "2mb",
                  "maximumError": "5mb"
                }
              ]
            },
            "ci": {
              "progress": false
            }
          }
        },
        "serve": {
          "builder": "@angular-devkit/build-angular:dev-server",
          "options": {
            "browserTarget": "app:build"
          },
          "configurations": {
            "production": {
              "browserTarget": "app:build:production"
            },
            "ci": {
              "progress": false
            }
          }
        },
        "extract-i18n": {
          "builder": "@angular-devkit/build-angular:extract-i18n",
          "options": {
            "browserTarget": "app:build"
          }
        },
        "test": {
          "builder": "@angular-devkit/build-angular:karma",
          "options": {
            "main": "src/test.ts",
            "polyfills": "src/polyfills.ts",
            "tsConfig": "tsconfig.spec.json",
            "karmaConfig": "karma.conf.js",
            "styles": [],
            "scripts": [],
            "assets": [
              {
                "glob": "favicon.ico",
                "input": "src/",
                "output": "/"
              },
              {
                "glob": "**/*",
                "input": "src/assets",
                "output": "/assets"
              }
            ]
          },
          "configurations": {
            "ci": {
              "progress": false,
              "watch": false
            }
          }
        },
        "lint": {
          "builder": "@angular-devkit/build-angular:tslint",
          "options": {
            "tsConfig": [
              "tsconfig.app.json",
              "tsconfig.spec.json",
              "e2e/tsconfig.json"
            ],
            "exclude": ["**/node_modules/**"]
          }
        },
        "e2e": {
          "builder": "@angular-devkit/build-angular:protractor",
          "options": {
            "protractorConfig": "e2e/protractor.conf.js",
            "devServerTarget": "app:serve"
          },
          "configurations": {
            "production": {
              "devServerTarget": "app:serve:production"
            },
            "ci": {
              "devServerTarget": "app:serve:ci"
            }
          }
        },
        "ionic-cordova-build": {
          "builder": "@ionic/angular-toolkit:cordova-build",
          "options": {
            "browserTarget": "app:build"
          },
          "configurations": {
            "production": {
              "browserTarget": "app:build:production"
            }
          }
        },
        "ionic-cordova-serve": {
          "builder": "@ionic/angular-toolkit:cordova-serve",
          "options": {
            "cordovaBuildTarget": "app:ionic-cordova-build",
            "devServerTarget": "app:serve"
          },
          "configurations": {
            "production": {
              "cordovaBuildTarget": "app:ionic-cordova-build:production",
              "devServerTarget": "app:serve:production"
            }
          }
        }
      }
    }
  },
  "cli": {
    "defaultCollection": "@ionic/angular-toolkit"
  },
  "schematics": {
    "@ionic/angular-toolkit:component": {
      "styleext": "scss"
    },
    "@ionic/angular-toolkit:page": {
      "styleext": "scss"
    }
  }
}

MIT License

Copyright (c) 2021 elvino

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

# -pushfire.io/lists
# Built application files
*.apk
*.ap_
*.aab

# Files for the ART/Dalvik VM
*.dex

# Java class files
*.class

# Generated files
bin/
gen/
out/
release/

# Gradle files
.gradle/
build/

# Local configuration file (sdk path, etc)
local.properties

# Proguard folder generated by Eclipse
proguard/

# Log Files
*.log

# Android Studio Navigation editor temp files
.navigation/

# Android Studio captures folder
captures/

# IntelliJ
*.iml
.idea/workspace.xml
.idea/tasks.xml
.idea/gradle.xml
.idea/assetWizardSettings.xml
.idea/dictionaries
.idea/libraries
# Android Studio 3 in .gitignore file.
.idea/caches
.idea/modules.xml
# Comment next line if keeping position of elements in Navigation Editor is relevant for you
.idea/navEditor.xml

# Keystore files
# Uncomment the following lines if you do not want to check your keystore files in.
#*.jks
#*.keystore

# External native build folder generated in Android Studio 2.2 and later
.externalNativeBuild

# Google Services (e.g. APIs or Firebase)
# google-services.json

# Freeline
freeline.py
freeline/
freeline_project_description.json

# fastlane
fastlane/report.xml
fastlane/Preview.html
fastlane/screenshots
fastlane/test_output
fastlane/readme.md

# Version control
vcs.xml

# lint
lint/intermediates/
lint/generated/
lint/outputs/
lint/tmp/
# lint/reports/

# Auto detect text files and perform LF normalization
* text=auto
