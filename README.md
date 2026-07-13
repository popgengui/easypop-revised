# easypop-revised

This repository ( https://github.com/popgengui/easypop-revised ) provides updated executables for the simulation program, EASYPOP, authored by F. Balloux, (c.f. Balloux, Francois. "EASYPOP (version 1.7): a computer program for population genetics simulations." Journal of heredity 92.3 (2001): 301-302 ).  

We thank Francois Balloux for sending us the source code, and allowing us to recompile it for more recent versions of operating systems, and to add some features.

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
 - Executable with tag 20250612 includes a fix for the spatial migration bug. 

## installation

- General Installation:

	- Installation is essentially a matter copying the executable file (named for your platform) into any folder in which you have sufficient permissions to run it.  If you add its full name and path to your PATH environmental variable, you can call it from any directory to which you want to write results files.  More simply, you can copy the executable to a folder to which you can both execute it and and write result files (example, most folders inside your home directory).  To run it you'll need to open a terminal (in Windows, a command prompt or powershell).  

   	- You can get a quick sense of running the program just by typing the name of the executable (apple and linux users, if you're running it from your current folder, precede the name with a dot and forward slash, ./) and follow the executable name with the single keyword, "prompt"   The program will prompt you through the simulation parameterization (press Ctl+c to abort).  See the UserGuide pdf of the original, and the easypop.revised.usage.txt for more details.


- Apple Intel and M1 executables.

   	- If you want to use it on a Mac with the newer M1 or M2 (the silicon version of the executable was compiled on an M1 Mac), you may want to try both the silicon and the intel version.  Although the Apple silicon version runs fine on my M1 Mac, I heard from a Mac M1 user that the silicon version gave a security warning, but the Intel version worked fine.  If you're not sure whether your Mac uses a silicon M chip, click the Apple menu icon, then  "About This Mac"  If you're Mac uses an M1 or M2 (Apple silicon) processor, you'll see the M1 or M2 noted just below the Mac name ( see https://support.apple.com/en-us/HT211814 ). 

   	- After downloading the executable, you may need to add exectuable attribute to the file.  Open a terminal, use "cd" to go to the folder that contains the executable and add executable privileges with the command,

		chmod +x <name of executable>

  	- Security issue: when you try to execute the command, you also may encounter a message that the file cannot be executed for security reasons.  On my Mac I clicked cancel on the denial message, then went to the apple menu icon, then clicked on System Settings, then,  Privacy and Security.  Scrolling down to Security, there was a warning message about the EASYPOP executable, and a button labeled "Allow Anyway".  I clicked on the button, was prompted to enter my password.  A second try at executing, I saw another warning message, but with an option to run it by clicking "open"  I was then able to execute the program, and it ran subsequently without warning messages.
	
## bugs and other issues 
- The executables dated 20250517, posted yesterday (05/19) and replaced today (05/20), have a bug that causes incorrect handling of configuration files that used older genotype output schemes.  The current executables dated 20250520 or after should correctly handle config files created by older 3.0 versions.
 - 05/29/2025.  For all versions of the  program, incorrect prgram behaviour is found to be likely when users select the spatial migration model as the second migration scheme.  The current exectuable, tagged 20250529, disallows this selection for a second migration scheme.  For details on the possible issues with this case, see https://github.com/popgengui/easypop-revised/issues
 - 06/13/2025.  Executables dated on or after 06/12/2025 (version 3.1.1, earliest date tag, 20250612) include a fix for the problem noted above, when spatial migration is selected as the second migration scheme.

## repository layout
Current executables are in platform specific subdirectories under "executables".  In the "docs" directory, you'll find the author's original user manual in pdf format, as well as documentation detailing the revised input methods and configuration file format.  Older versions of this revised easypop are found in the "old.executable.versions" directory.

## Statement about lack of Warrenty
THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
