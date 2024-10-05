# ELF-and-PE
ELF is short for Executable and Linkable Format. It’s a format used for storing binaries, libraries, and core dumps on disks in Linux and Unix-based systems.

Moreover, the ELF format is versatile. Its design allows it to be executed on various processor types. This is a significant reason why the format is common compared to other executable file formats.

Each file contain headers (ELF header, Section header, Program header etc) . Program divided into segments and each segments contain sections (.text,.data, etc)

PE stands for Portable Executable, it’s a file format for executables used in Windows operating systems, it’s based on the COFF file format (Common Object File Format).

Not only .exe files are PE files, dynamic link libraries (.dll), Kernel modules (.srv), Control panel applications (.cpl) and many others are also PE files.

A PE file is a data structure that holds information necessary for the OS loader to be able to load that executable into memory and execute it.

Each file contain headers (DOS Header, File Header, Optional Header) and actual data divided into segments (.text,.data etc)

# Traditional Anti-Virus 
Traditional anti-virus software have database of Malware signatures (signature is string,a piece of code, comment anything that a malicious file contain and using it
we can figure out whether a file is malicious or not. Required different versions of same malware and expert ,who can figure out the signature by analyzing this files).
Program is declared malware when a signature is found in the scanned program's code. But is fails in case of zero-day malware and variants of existing malware.

# Strings UNIX tool
Strings are recognized by looking for sequences of at least 4 (by default) printable characters terminating in a NULL character. The files can be of regular text files or binary files such as executables. It can be used on object files and core dumps. strings is mainly useful for determining the contents of non-text files.

# What we are doing ? 
We are taking out the header information from this files using libraries like elftools, pefile. We also use strings tool to find the printable character hiding behind
binary object,executable files. Then creating a dataset using this both information. And then training models on this dataset which can predict whether the file is 
malicious or not.
