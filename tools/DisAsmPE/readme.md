#### .NET Micro Framework Disassembler sample
This project contains a utility for loading, parsing and disassembling a .NET Micro framework PE file.
While this isn't intended to function as a full production disassembler like ILDasm or ILSpy, it does serve
as a stand alone project to aid in comprehending the NETMF PE file binary data format.

There are two basic forms of files containing .NET Micro Framework metadata and IL code. The .pe files and
.DAT files.

###### PE Files
PE files correspond to a single assembly (either a dll or exe). These are generated by the
NETMF Metadata Processor during the code compilation process of a NETMF project. Details of the PE
are available in the [PE File Format](https://github.com/NETMF/netmf-interpreter/wiki/PeFileFormat) topic.

###### .DAT Files
.DAT files are used to group multiple assemblies into a single data file as a raw memory block when generating
the device firmware images. The format of a DAT file is a set of PE files concatenated together with each PE file
starting on a 32 bit boundary (Thus there are up to 3 bytes of padding between each PE file in a .DAT file)