## ✨ Using

### Creating a new Python project

To create a new Python project with this template:
1. Install the latest [Cruft](https://github.com/cruft/cruft) in your Python environment with:
   ```sh
   pip install cruft
   ```
   or install with pipx
   ```sh
    pipx install cruft
   ```
2. Create a new repository and clone it locally.
3. In the directory that contains the cloned repository, run:
   ```sh
   cruft create -f https://github.com/asikeero/python-template
   ```
4. _Optional:_ if your repository name differs from your project's slugified name, you will need to copy the scaffolded project into the repository with:
   ```sh
   cp -r {package-name}/ {repository-name}/
   ```

### Updating your Python project

To update your Python project with the latest template:
1. Run `cruft update` to update your project with the latest template.
2. If any of the updates failed, resolve them by inspecting the generated `.rej` files.