Revision to executables dated 01/2024:
- When parametrizing the migration scheme, hierarchical island, the writing of parameter, per_archipelago_number_of_populations to a configuration file was suppressed in the case in which the user responds  with "y" when setting the param, same_number_populations_each_archipelago.  In the case of uniform number of pops per archipelago, the configuration file should not contain an array listing, as the program ignores this and simply divides the number of populations by the number of archipelagos.  Further, in the revised executable, the program does not look for such an array when if finds the "y" value for same_number_populations_each_archipelago.  In the older version, the program did (incorrectly) look for an array giving per_archipelago_number_of_populations when the same_number_populations_each_archipelago was set to "y"  Hence, the older executional will throw an error if a config file with the noted settings was created with the new version. Note that this issue does not arise when the hierarchical island model is chosen as a second migration scheme.


Revision to executables dated 03/2024:
- A new simulation output option provides a gen and dat file for each generation, rather than the default (former) behavior in which only one gen and dat file is produced, for the last generation.  This revision adds the new parameter to the configuration file.  Configuration files created with this new revision can be run using older executables, but the new option entry is ignored and only the last generation produces a gen and dat file.  


Revision to executables dated 10/2024
- A new option to save only one of the two genotype file types (gen or dat).

Revision to executables dated 05/2025, version incremented to v3.1
- Adds new options to (1) select for which generations the program should output genotype files, and (2) if the user selects gen file output (with or without dat files), select whether gen files are grouped by generation (the original and default case, in which each "pop" entry represents a different population), or by population (each "pop" entry represents a generation, this gen file grouping added to facilitate temporal analysis by programs such as NeEstimator).  Note that dat file format is available only in the original format.
- Fixed a bug in a scenario in which the user selects haplo-diploid ploidy and is using the prompts and writing to a configuration file.  If the user answers "no" as to whether all populations have the same size, and then gives numbers per-population for queens, males, and workers, the program was correctly writing to the file the lists of sizes for all three individual types. However, when reading the configuration file, the program was stopping on an error, failing to find the list of numbers of workers per population.  This is now fixed.
 - Update on the 05/2025 executables:  the executables dated 20250517, posted yesterday (05/19) and replaced today (05/20), have a bug that causes incorrect handling of configuration files that used older genotype output schemes.  The current executables dated 20250520 should correctly handle config files created by older 3.0 versions.

 - Update on all executables.  A bug was found that applies to all versions as of 05/28/2024.  Exact bug behaviour is not yet fully known, but review of the code suggests that users should not select the spatial migrationn model (type 6) as a second migration scheme.  For more details, please see the issues section of the easypop.revised github at https://github.com/popgengui/easypop-revised/issues


