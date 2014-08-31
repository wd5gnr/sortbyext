Copyright 2014 by Al Williams (al.williams@awce.com
Distributed under the terms of the GNU General Public License

    This file is part of sortbyext

    sortbyext is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <http://www.gnu.org/licenses/>.



sortbyext by Al Williams (al.williams@awce.com)

Usage:

sortbyext [-d target_directory] [-m] [-q] [-n] file [file...]

Files with extensions cause a directory to be made
corresponding to the extension and the file moved
there.

-d sets the target directory

-m causes the smallest extension to be used
(e.g., x.tar.gz is a .gz file not a tar.gz file)

-n Prevents overwriting an existing file

-q Inhibits output messages


Exclusions, Aliases and Mime Types

The program looks for a file in your home directory:


~/.config/sortbyext.conf

If this is not found, it then looks for:


/usr/local/share/sortbyext/sortbyext.conf

If this is not found, it then looks for

/usr/share/sortbyext/sortbyext.conf

If one is found, the following processing occurs on a file
named foo.bar with mime type application/example


1) If the configuration file contains the line -bar, the script skips this file


2) If the configuration file contains the line -application/example, the script skips this file


3) If the configuration file contains the a matching line it will use 
the specified alias name as the directory name. Matching lines for this example
would include:


=test:bar


=test:application/example


=test:application/ 


All of these lines would match the file and cause it to be sorted into
directory test 


4) If there is no match on #3, and the file has a usable extenstion
The program uses the extension name (e.g., pdf) as the sort directory


5) If there is a sort directory set in step 3 or 4, the file is moved into it


You can copy /usr/local/share/sortbyext/sortbyext.conf to your ~/.config directory to customize. Comments in the file will further explain the format.

Post at Ubuntuforums: http://ubuntuforums.org/showthread.php?t=2242218
