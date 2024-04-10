## Task 1: SSH Keygen Method

1. Open your terminal or command prompt.
2. Run the following command to generate an **Ed25519** SSH key pair:
    ```
    ssh-keygen -t ed25519 -C "<comment regarding the key>"
    ```
    - You can specify a custom path for the keys (default: `./.ssh/ed25519`).
    - Set a password for the generated key.
3. Two keys will be created:
    - `ed25519` (Highly confidential, do not expose)
    - `ed25519.pub` (Safe to display)

---

## Task 2: GITPlay

1. Create a new repository on GitHub.
2. In the repository settings, add your SSH keys.
3. Navigate to the "SSH keys" section and copy the contents of your public key (`ed25519.pub`).

### Git Commands:

1. Verify that Git is installed:
    ```
    which git
    ```
    - If not installed, install Git.
2. Create a new file containing a list of servers.
3. Add that file to Git using the following commands:
    ```
    git add <filename>
    git commit -m "<message>"
    git push origin master/main
    ```

---

## Task 3:

1. Configure `ansible.cfg`.
2. Under the `[defaults]` section, specify the path to your inventory file and the private key for Ansible:
    ```
    [defaults]
    inventory = inventoryServerlist
    private_key_file = ~/.ssh/ansible
    ```

---

## Task 4:

Run Ansible commands in shorthand form:

- Example: Ping all hosts
    ```
    ansible all -m ping
    ```

- Full command:
    ```
    ansible all -i inventoryServerlist -m <module_name>
    ```
