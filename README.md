# Course Converter Tool

**Student**: Tingyang Liu - s4827401

## Overview

A command-line tool that converts OpenEdx OLX course packages into LiaScript (`course.md` + `media/`) using a functional JavaScript pipeline.

## Features

- Converts OpenEdx courses to LiaScript format
- Processes single files or entire directories
- Handles HTML content, video files, and various question types
- Copies media files and corrects file paths
- Includes comprehensive testing suite
- Implements functional programming principles

**Note**: This converter supports both .tar.gz and .zip course export files. For .zip files, the content is automatically extracted and processed.

## Conversion Mapping

| Input | Output |
|-------|--------|
| Course title | # Heading |
| Chapter | ## Subheading |
| Content | ### Smaller heading |
| HTML | Regular markdown |
| Videos | YouTube embeds |
| Questions | Interactive format |
| Hidden content | Filtered out |

## Installation

```bash
npm install
```

## Usage

### Convert Single Course File

```bash
node courseconverter.js inputcourses/simple.tar.gz outputcourses
node courseconverter.js inputcourses/simple.zip outputcourses
```

### Convert Entire Input Directory

```bash
node courseconverter.js inputcourses/ outputcourses
```

## Output Structure

Converted courses are placed in the output folder, with each course in its own subfolder:

```
outputcourses/
├── course_code_1/
│   ├── course.md
│   └── media/
│       ├── image1.jpg
│       └── video1.mp4
└── course_code_2/
    ├── course.md
    └── media/
        └── ...
```

## Testing

```bash
npm test
```

The test suite covers:
- XML parsing functionality
- Course code extraction
- HTML to Markdown conversion
- Image path processing
- Video conversion
- Problem conversion (all types)
- LiaScript Markdown generation
- Error handling mechanisms
- Edge case scenarios

## Architecture

The tool is structured with small, focused functions:
- Parse the XML files
- Build an index of all content
- Convert each component to markdown
- Assemble the final output
- Generate one course.md per course

**File Support**: Automatically handles both .tar.gz and .zip course packages.

### Error Handling

- XML parsing errors are caught and handled
- File extraction errors are reported
- Missing components fall back gracefully

## Dependencies

- **tar**: Handle .tar.gz file extraction
- **fast-xml-parser**: Efficient XML file parsing
- **node-html-markdown**: Convert HTML to Markdown
- **fs-extra**: Enhanced file system operations
- **jest**: Testing framework

## Development Notes

### Code Structure

```
├── courseconverter.js      # Main conversion script
├── courseconverter.test.js # Test file
├── package.json           # Project configuration
├── README.md              # Project documentation
└── inputcourses/          # Input courses directory
    └── course/            # Sample course
        ├── course.xml     # Course configuration file
        ├── chapter/       # Chapter directory
        ├── sequential/    # Sequential directory
        ├── vertical/      # Vertical content directory
        ├── problem/       # Problem directory
        ├── html/          # HTML content directory
        └── video/         # Video directory
```

### Future Extensions

- Add new problem types in `convertProblem`
- Add new unit types in `processVertical`
- Maintain small, focused functions for testability

## External Resources

### Generative AI Usage

I used generative AI tools for minor assistance with planning and wording only (e.g., brainstorming test ideas, rephrasing comments). All program logic, algorithms, and code were written and verified by me. No AI-generated code was included without review, and I am fully responsible for the final implementation.
