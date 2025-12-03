Watchdog v1.5 Changelog
Major Changes
1. Unified Configuration System
NEW: Single watchdog.conf file replaces separate watch_files.txt and watch_procs.txt

NEW: Configuration organized into sections: [watch_procs], [watch_files], [whitelist_files], [whitelist_folders]

NEW: Global settings section for configurable options (starting with clean_trash)

2. Whitelist Protection System
NEW: [whitelist_files] section - protects specific files from deletion/monitoring

NEW: [whitelist_folders] section - excludes entire folders from monitoring

IMPROVED: Watchdog's own files are protected by default in whitelist

3. Configurable Features
NEW: clean_trash = true/false setting to enable/disable trash folder cleaning

IMPROVED: More user control through configuration file

4. Backward Compatibility
NEW: Automatic migration from old config files (watch_files.txt, watch_procs.txt) to new format

IMPROVED: Maintains existing behavior when upgrading

Code Improvements
5. Fixed Monitoring Logic
FIXED: Removed hardcoded exclusion of /root/watchdog_config folder

IMPROVED: Config folder now only excluded when explicitly added to [whitelist_folders]

FIXED: Updated find_files_by_name() and get_current_file_state() functions

6. Enhanced User Feedback
NEW: Status display for trash cleaning (ENABLED/DISABLED)

NEW: Visual feedback for config file recreation

IMPROVED: Better initialization messages showing config status

7. Bug Fixes
FIXED: Ternary operator syntax error in main() function

IMPROVED: More robust error handling for missing config files

FIXED: Proper whitelist checking logic

File Structure Changes
Removed Files:
/root/watchdog_config/watch_files.txt

/root/watchdog_config/watch_procs.txt

New Files:
/root/watchdog_config/watchdog.conf (main configuration)

Modified Files:
/root/watchdog_config/total_sizes.cfg (still used for file indexing)

/root/watchdog_config/monitor.log (enhanced logging)
