# Linux Fundamentals Cheat Sheet
This cheatsheet covers essential Linux commands for file navigation, permission management, package handling, and networking diagnostics, compiled as a deliverable for Task 1 of the Ethical Hacking & Cybersecurity Internship.

### Print Working Directory (NAVIGATION)
- **Command:** `pwd`
- **Usage Example:** `pwd`
- **Explanation:** Returns the absolute path of the current directory you are positioned in. Extremely useful in pentesting to confirm file placement paths.

### List Directory Contents (NAVIGATION)
- **Command:** `ls`
- **Usage Example:** `ls -la /var/www`
- **Explanation:** Lists subdirectories and files in a path. The `-l` flag creates a detailed list layout, and `-a` reveals hidden configuration files (prefixed with ".").

### Change Working Directory (NAVIGATION)
- **Command:** `cd`
- **Usage Example:** `cd /etc/network`
- **Explanation:** Shifts operating terminal focus to the user specified path. `cd ..` backs out one directory tier toward the root directory.

### Make Directory (NAVIGATION)
- **Command:** `mkdir`
- **Usage Example:** `mkdir -p /root/labs/task1`
- **Explanation:** Declares a new folder structure inside target directory. Using the `-p` flag recursively establishes nested parents if they don't exist yet.

### Change File Mode Bit Permissions (PERMISSIONS)
- **Command:** `chmod`
- **Usage Example:** `chmod +x attack_script.sh`
- **Explanation:** Edits read (4), write (2), and execute (1) parameters. Adding key `+x` marks administrative scripts executable so hosts can run them.

### Change File Owner and Group Rights (PERMISSIONS)
- **Command:** `chown`
- **Usage Example:** `sudo chown root:root secret.txt`
- **Explanation:** Transfers security ownership of target file assets. The syntax maps `[owner-name]:[group-name]` directly to restrict normal accounts.

### Inspect Access Rights & Attribute Rows (PERMISSIONS)
- **Command:** `ls -l`
- **Usage Example:** `ls -l /etc/shadow`
- **Explanation:** Prints strict permissions grids (`rwxr-xr-x`) mapping specific security limits back to owner accounts, user groups, and others.

### Refresh Package Repository Indexes (PACKAGES)
- **Command:** `apt-get update`
- **Usage Example:** `sudo apt-get update`
- **Explanation:** Queries configured repositories to build local listings of the latest available software packages. Mandatory step before major updates.

### Install Pre-Compiled Binaries (PACKAGES)
- **Command:** `apt install`
- **Usage Example:** `sudo apt install wireshark nmap dsniff -y`
- **Explanation:** Pulls compiled tools directly from standardized mirrors. The `-y` flag answers yes to prompts, avoiding install freezes.

### Install Offline Debian Binary Packages (PACKAGES)
- **Command:** `dpkg -i`
- **Usage Example:** `sudo dpkg -i package_file.deb`
- **Explanation:** Manually extracts and registers raw standalone install objects (.deb). Standard deployment route when working off-grid.

### Configure/Display Network Interface parameters (NETWORKING)
- **Command:** `ifconfig`
- **Usage Example:** `ifconfig eth0`
- **Explanation:** Retrieves logical addressing properties, operational duplex rates, MTU configurations, and hardware MAC address footprints.

### Diagnose Logical Interface Connectivity (ICMP Echo request) (NETWORKING)
- **Command:** `ping`
- **Usage Example:** `ping -c 5 192.168.1.3`
- **Explanation:** Queries a logical endpoint node. Standard parameter checks. Using `-c 5` issues exactly five test pings before summarizing packet results.

### Print Network Connections & Routing Tables (NETWORKING)
- **Command:** `netstat`
- **Usage Example:** `netstat -tulnp`
- **Explanation:** Locates active listeners. Flags map to `t`cp, `u`dp, `l`isteners, `n`umeric, and `p`rogram process IDs. Crucial for backtracking backdoors.

### Audit Network Delivery Paths (Diagnostic Trace) (NETWORKING)
- **Command:** `traceroute`
- **Usage Example:** `traceroute 192.168.1.3`
- **Explanation:** Measures time delays across all routing nodes between host terminals and target endpoints. Finds latency blocks in network lines.
