# Shells

A **shell** is a command-line interface that allows you to interact with the operating system by entering commands.

### Identifying Your Shell

```bash
echo $SHELL
```

Displays your current/default shell.

```bash
history
```

Displays previously executed commands.

```bash
cat /etc/shells
```

Lists the shells installed and available on the system.

### Switching Shells

To temporarily switch shells, simply type the shell name:

```bash
zsh
fish
bash
```

The shell will change for the current session.

To **permanently change your default shell**:

```bash
chsh -s /usr/bin/<shellname>
```

Example:

```bash
chsh -s /usr/bin/zsh
```

> **Default shell:** Bash (on most Linux distributions)

---

## Bash — Bourne Again Shell

**Bash** stands for **Bourne Again Shell** and is the default shell on many Linux systems.

* Widely supported and commonly used
* Good for general command-line usage
* Supports scripting
* Basic level of customization
* Excellent compatibility with existing Linux scripts

```bash
bash
```

---

## Fish — Friendly Interactive Shell

**Fish** stands for **Friendly Interactive Shell** and is designed to be easy to use.

* Beginner-friendly
* Automatic command suggestions
* Advanced tab completion
* Syntax highlighting
* Auto spell correction
* Minimal configuration required

```bash
fish
```

**Best suited for:** Users who want a convenient and beginner-friendly interactive shell.

---

## Zsh — Z Shell

**Zsh** is an advanced shell that combines many features found across different shells.

* Advanced tab completion
* Command history
* Auto spell correction
* Highly customizable
* Supports shell scripting
* Can be extended with plugins and frameworks
* Extensive customization can make it slower than simpler shells

```bash
zsh
```

**Best suited for:** Users who want a powerful and highly customizable shell.

### Quick Comparison

| Shell    | Main Strength                            |
| -------- | ---------------------------------------- |
| **Bash** | Compatibility & scripting                |
| **Fish** | Beginner-friendly interactive experience |
| **Zsh**  | Advanced features & customization        |
