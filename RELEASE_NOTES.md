This file contains a high-level description of this package's evolution.
Entries are in reverse chronological order (most recent first).

VERSION         COMMENTS
-------         --------


### 4.4-rc1 	Released 2013-10-06

* Added missing error codes for DAP and some netCDF-4 errors

* Fixed some documentation for F77 API, added make rule for creating
		netcdf-f77 HTML files.

### 4.4-beta5 	Released 2013-08-27

* Added configuration files to github distribution.

### 4.4-beta4      

* Moved to GitHub from Subversion, the location of the new GitHub repository is at: http://github.com/Unidata/netCDF-Fortran

* Parallel-build portability fixes, particularly for
		OpenMPI and gcc/gfortran-4.8.x on the Mac.  Also added
		test from Reto Stöckli for NCF-250 bug, demonstrating
		it was fixed in previous commit.
		
* Add support for NF\_MPIIO, NF\_MPIPOSIX, NF\_PNETCDF, and
		NF\_FILL\_UINT in the data files.

* Add support for nf\_inq\_path.

* Add a pre-processor macro that can be used to bypass
		the home-brew C_PTRDIFF_T definition and use the
		standard one for compilers that support it.

* Fix a potential bug in nf\_attio to call the \_long
		version of some puts/gets instead of the \_int
		version. These were inside INT1\_IS\_C\_LONG and
		INT2\_IS\_C\_LONG ifdef blocks so they would have only
		showed up when those macros were true.

### 4.4-beta3	Released 2012-12-07

		Fixed bug that "make -j check" fails, but "make check"
		works fine.

		Fixed build problems resulting from syncing with
		separate C distribution.

		Synchronize with all changes made to version 4.2 since
		its release.

### 4.4-beta2	Released 2012-06-29

		Made handling of --disable-f03 more transparent.

		Fixed adding flags for parallel I/O for MPI from David
		Warren.

		Removed all the old C code that's not needed for this
		separate distribution.

		Inadvertently broke the build until syncing with C
		distribution in later beta release.

### 4.4-beta1	Released 2012-03-02
	        
	        Version 4.4 is the first release to support
                fortran 2003 and to use the ISO C Bindings available
                in fortran 2003 to replace the older C code wrappers.
	        Congratulations and thanks to Richard Weed at 
                Mississippi State University, who is the author of
                new code.
	        See the file README_F03_MODS for a more complete
                description of the changes. Many changes to the build
                structure have been made at the same time as the new
                2003 code has been inserted.
	        
                As part of the fortran 2003 refactor, the directory
                structure has been significantly modified.  All the previous
                F90 C wrapper code has been moved to the "libsrc" directory.
                All of the fortran code has been moved to the "fortran"
                directory. The directories names F77 and F90 have been
                removed. The most important consequence of this refactor is
                that pure Fortran77 compilers are no longer supported. It is
                assumed that the compiler supports at least Fortran 90 and
                also Fortran 77.  If it also supports the ISO C Bindings,
                then the new 2003 code is used instead of the older C wrappers.
