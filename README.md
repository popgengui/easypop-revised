# easypop-revised

This repository ( https://github.com/popgengui/easypop-revised ) provides updated executables for the simulation program, EASYPOP, authored by F. Balloux, (c.f. Balloux, Francois. "EASYPOP (version 1.7): a computer program for population genetics simulations." Journal of heredity 92.3 (2001): 301-302 ).

## revisions
These executables have been revised and recompiled by T. Cosart for more current Linux, Windows, and Apple Mac platforms.  It includes two for Mac platforms, one compiled on an Intel cpu, the other on the silicon, M1 cpu. The original's Windows GUI interface has been replaced by a terminal (console) interface that mimics the prompt/response format of the original, which was itself essentially a terminal inside an application window.  Further, it adds the following features:

- the program can write a simulation configuration file. You can then run the simulation based on the configuration file, as an alternative to stepping through the prompt/response procedure.  For details, see the easypop.revised.usage.txt file in this repository's "doc" directory.

- In executables compiled since 03/2024, the program prompts you with an option to produce genotype files for each generation, rather than the default behavior, which gives you genotype files only for the last generation.  A note of caution:  requesting per-generation genotype files can result in a very large amount of output, since the number of genotype output files will total the number of generations times the number of replicates, doubled if the program is producing both both genotype file types.

- In executables compiled since 10/2024, the program prompts you to specify whether it should produce \*.gen, \*.dat, or both (formerly the only option) of its genotype output files types.

- In executables compiled since 05/2025 (version 3.1), there are new options to (1) select for which generations the program should output genotype files, and (2) if the user selects gen file output (with or without dat files), select whether gen files are grouped by generation (the original and default case, in which each "pop" entry represents a different population), or by population (each "pop" entry represents a generation, added to facilitate temporal analysis by programs such as NeEstimator).  
	- Details on the new vs old gen file format
		- The leading field in the genotype entries prepends a "g" (eg. "g1" for generation 1), instead of the
             population number, seen in the original format.

		- The numbers listed in the header represent, in order: 
                population number, number of loci, number of alleles, 
                and number of digits coding the alleles.  

		- In the original format the header numbers represent:
                number of populations, number of loci, number of alleles, 
                number of digits coding the alleles.         

	 Note that no new options were added for dat file format, which is still only available in the original format.

 - Update on the 05/2025 executables: the executable added today 05/29/2025 (tagged 20250529), is revised to disallow using the spatial migration scheme as the second migration scheme (i.e. when the user opts to change the migration scheme).  This is added due the the issue noted below.
	
## bugs and other issues 
- The executables dated 20250517, posted yesterday (05/19) and replaced today (05/20), have a bug that causes incorrect handling of configuration files that used older genotype output schemes.  The current executables dated 20250520 or after should correctly handle config files created by older 3.0 versions.
 - 05/29/2025.  For all versions of the  program, incorrect prgram behaviour is found to be likely when users select the spatial migration model as the second migration scheme.  The current exectuable, tagged 20250529, disallows this selection for a second migration scheme.  For details on the possible issues with this case, see https://github.com/popgengui/easypop-revised/issues
 - 06/13/2025.  The latest executable (version 3.1.1, date tag, 20250612) includes a fix for the problem noted above, when spatial migration is selected as the second migration scheme.
## repository layout
Current executables are in platform specific subdirectories under "executables".  In the "docs" directory, you'll find the author's original user manual in pdf format, as well as documentation detailing the revised input methods and configuration file format.  Older versions of this revised easypop are found in the "old.executable.versions" directory.


