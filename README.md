\# OSS Audit --- Git Software

\### Open Source Software Capstone Project \| VITyarthi

\-\--

\*\*Student Name:\*\* \[Priyanshu Abhinav\]

\*\*Registration Number:\*\* \[24BHI10035\]

\*\*Chosen Software:\*\* Git Software (Version Control System)

\*\*Course:\*\* Open Source Software (NGMC)

\-\--

\## About This Project

This repository consists of five shell scripts from the \*\*Open Source
Audit\*\* capstone project, showing the practical Linux and shell
scripting skills which are rooted in the \*\*Git\*\* ecosystem --- the
version control system (Open Source) created by Linus Torvalds in 2005.

\-\--

\## Repository Structure

\`\`\`

oss-audit-\[24BHI10035\]/

│

├── README.md ← This file

│

└── scripts/

├── script1_system_identity.sh ← Script 1: System Identity Report

├── script2_package_inspector.sh ← Script 2: FOSS Package Inspector

├── script3_disk_auditor.sh ← Script 3: Disk and Permission Auditor

├── script4_log_analyzer.sh ← Script 4: Log File Analyzer

└── script5_manifesto_generator.sh ← Script 5: Open Source Manifesto
Generator

\`\`\`

\-\--

\## Environment Setup

\### Requirements

\- A Linux system (Ubuntu 20.04+ / RHEL / Fedora / Debian / any modern
distro)

\- Bash shell (version 4.0 or higher --- standard on all modern Linux)

\- Git installed (\`sudo apt install git\` or \`sudo dnf install git\`)

\- Basic utilities: \`uname\`, \`whoami\`, \`du\`, \`df\`, \`ls\`,
\`grep\` (pre-installed on all Linux)

\### Verify Bash version

\`\`\`bash

bash \--version

\`\`\`

\### Make all scripts executable

Once we clone this repository, we will have to run this command at first
to allow execute permissions on all of the scripts.

\`\`\`bash

chmod +x scripts/\*.sh

\`\`\`

\-\--

\## Scripts --- Description and How to Run

\-\--

\### Script 1: System Identity Report

\*\*File Name:\*\* \`scripts/script1_system_identity.sh\`

\*\*What it does:\*\*

This script will display a nice little welcome screen with real-time
system information, such as your distro\'s name, kernel version, who is
currently logged in, their home directory, system uptime, current time,
and OS license.

\*\*Key Concepts:\*\* Variables, command substitution \`\$()\`,
\`/etc/os-release\` parsing, \`echo\`.

\*\*How to run:\*\*

\`\`\`bash

bash scripts/script1_system_identity.sh

\`\`\`

\*\*Expected output:\*\*

A formatted system identity report printed to the terminal.

\-\--

\### Script 2: FOSS Package Inspector

\*\*File Name:\*\* \`scripts/script2_package_inspector.sh\`

\*\*What it does:\*\*

This will inspect a specified package, defaulting to \`git\`, to let you
know if you have it installed, what version you\'re running, and include
a little philosophy on its place in the world of FOSS.

\*\*Concepts used:\*\* \`if-then-else\`, \`case\` statement,
\`dpkg\`/\`rpm\` package queries, pipe with \`grep\`.

\*\*How to run:\*\*

\`\`\`bash

bash scripts/script2_package_inspector.sh

\`\`\`

\*\*To check a different package\*\*, Simply change \`PACKAGE\` variable
at the top of this script to whatever we want to inspect:

\`\`\`bash

PACKAGE=\"vlc\" \# or firefox, python3, mysql, etc.

\`\`\`

\-\--

\##

\### Script 3: Disk and Permission Auditor

\*\*File Name:\*\* \`scripts/script3_disk_auditor.sh\`

\*\*What it does:\*\*

This script will loop through a list of important system directories,
reporting on the current permissions, owners, groups, and disk usage of
those directories.

\*\*Concepts used:\*\* \`for\` loop, \`ls -ld\`, \`du -sh\`, array
iteration, conditional directory checks, \`awk\`, \`cut\`.

\*\*How to run:\*\*

\`\`\`bash

bash scripts/script3_disk_auditor.sh

\`\`\`

\*\*Note:\*\* Some directories, such as /var/log, need to be run with
sudo in order for the disk usage report to work correctly:

\`\`\`bash

sudo bash scripts/script3_disk_auditor.sh

\`\`\`

\-\--

\### Script 4: Log File Analyzer

\*\*File Name:\*\* \`scripts/script4_log_analyzer.sh\`

\*\*What it does:\*\*

This script will take a path to a log file and a keyword to search for
as command-line arguments, open the file, and report on the number of
times that keyword is found in the file, ignoring case.

\*\*Concepts used:\*\* \`while read\` loop, counter variables, \`grep\`,
\`if-then\`, \`tail\`, retry loop simulation, command-line arguments
(\`\$1\`, \`\$2\`).

\*\*How to run:\*\*

\`\`\`bash

\# Basic usage --- searches for \"error\" by default

bash scripts/script4_log_analyzer.sh /var/log/syslog

\# With a custom keyword

bash scripts/script4_log_analyzer.sh /var/log/syslog \"warning\"

\# On systems using journald (no /var/log/syslog), try:

bash scripts/script4_log_analyzer.sh /var/log/kern.log

\# Create a test log file if needed

echo -e \"INFO: system started\\nERROR: disk full\\nWARNING: low
memory\\nERROR: connection refused\" \> /tmp/test.log

bash scripts/script4_log_analyzer.sh /tmp/test.log error

\`\`\`

\-\--

\### Script 5: Open Source Manifesto Generator

\*\*File Name:\*\* \`scripts/script5_manifesto_generator.sh\`

\*\*What it does:\*\*

It will ask three questions in interactive mode and creates a customized
open-source philosophy based on the user's response. It will then save
the response in a \`.txt\` file having the name
\`manifesto\_\<username\>.txt\` and prints it inside the terminal.

\*\*Concepts used:\*\* \`read\` for interactive input, string
concatenation, file redirection (\`\>\` and \`\>\>\`), \`date\` command,
alias concept (demonstrated via comment), input validation with
\`while\`.

\*\*How to run:\*\*

\`\`\`bash

bash scripts/script5_manifesto_generator.sh

\`\`\`

By following these three prompts. The manifesto will be saved as
\`manifesto\_\<yourusername\>.txt\` in the current directory.

\-\--

\## Dependencies

\| Dependency \| Purpose \| Pre-installed? \|

\|\-\-\-\-\-\-\-\-\-\-\--\|\-\-\-\-\-\-\-\--\|\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--\|

\| \`bash\` \| Run all scripts \| Yes (all Linux) \|

\| \`git\` \| Script 2 package check \| Install if needed \|

\| \`uname\` \| Kernel version (Script 1) \| Yes \|

\| \`whoami\` \| Username (Scripts 1, 5) \| Yes \|

\| \`dpkg\` / \`rpm\` \| Package info (Script 2) \| Depends on distro \|

\| \`du\`, \`ls\`, \`df\` \| Disk/permission info (Script 3) \| Yes \|

\| \`grep\`, \`tail\` \| Log analysis (Script 4) \| Yes \|

\| \`date\` \| Timestamp (Script 5) \| Yes \|

\-\--

\## Tested On

\- Ubuntu 22.04 LTS (bash 5.1)

\- Debian 11 (bash 5.1)

\- Fedora 39 (bash 5.2)

\-\--

\## Academic Integrity

All the scripts are original work has been done by the student above.
They developed, tested, and documented individually as part of the
VITyarthi OSS Capstone Project.

\-\--

\*\"Every tool you will use in your career was shaped by people who
chose to build in the open and share their work freely.\"\*

--- VITyarthi OSS Course
