# Course Converter Tool

**Student**: Tingyang Liu - s4827401

## What it does

A tool that converts OpenEdx courses to LiaScript format. It's pretty straightforward - you give it some course files and it spits out Markdown that works with LiaScript.

## What it handles

- Converts OpenEdx courses to LiaScript
- Works with single files or whole folders
- Handles HTML, videos, and different question types
- Copies images and fixes paths
- Has some tests to make sure it works
- Written in a functional style

**Note**: This converter supports both .tar.gz and .zip course export files. For .zip files, the content is automatically extracted and processed.

## How it converts stuff

| Input | Output |
|-------|--------|
| Course title | # Heading |
| Chapter | ## Subheading |
| Content | ### Smaller heading |
| HTML | Regular markdown |
| Videos | YouTube embeds |
| Questions | Interactive format |
| Hidden stuff | Gets filtered out |

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

Converted courses go to the output folder, each course in its own subfolder:

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

## Run Tests

```bash
npm test
```

Tests cover the key pieces:
- XML parsing
- Course code extraction
- HTML to Markdown conversion
- Image path processing
- Video conversion
- Problem conversion (all types)
- LiaScript Markdown generation
- Error handling
- Edge cases

## How it works

The code is split into small functions that each do one thing:
- Parse the XML files
- Build an index of all the content
- Convert each piece to markdown
- Put it all together
4. Convert HTML/Video/Problem to Markdown
5. Write one course.md per course

**File Support**: Automatically handles both .tar.gz and .zip course packages.

### Error handling

- XML parse errors are caught
- File/untar errors are reported
- Missing pieces fall back safely

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

### Extend later

- Add new problem types in `convertProblem`
- Add new unit types in `processVertical`
- Keep converters as small functions so tests stay simple

## AI Usage Declaration

### Generative AI usage (short)

- Used AI (Claude Sonnet in Cursor) for learning tips, structure ideas, and test ideas
- Core logic written by the developer; AI did not inject hidden code
- Final code follows the assignment’s functional goals

### Other External Resource References

- **LiaScript Documentation**: Referenced LiaScript Markdown syntax specifications
- **OpenEdx Documentation**: Understood OLX format structure
- **Jest Documentation**: Learned testing framework usage methods

