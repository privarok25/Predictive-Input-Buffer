# Build a Windows .geode package

This bundle contains source code, not a precompiled `.geode` binary. The included GitHub Actions workflow builds the package in a clean Windows runner.

The source includes the earlier transient-input-state reset patch plus a guard against duplicate input-state notifications (for example, repeated key-down events while a key is already held). This is intended to prevent duplicate events being treated as separate clicks. It has **not** been compiled or tested in Geometry Dash in this environment, so test it before relying on it.

1. Create a new repository on GitHub while signed in.
2. Upload the contents of this folder (including the hidden `.github` folder) to the repository's root. The easiest route is to extract the ZIP on a PC and use GitHub's web upload, or push the folder with Git.
3. Open the repository's **Actions** tab and enable workflows if GitHub asks.
4. Open **Build Geode mod** and click **Run workflow** (or wait for the first push build).
5. When the run finishes successfully, open the run and download the artifact named `Predictive-Input-Buffer-Windows`.
6. Extract the artifact; it should contain the `.geode` file. Put it in your Geometry Dash Geode mods folder and restart/reload Geode.

If the workflow fails, download the build log and use the first CMake/compiler error to diagnose the issue. A successful CI build does not replace in-game testing.
