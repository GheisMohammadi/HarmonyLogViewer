# Harmony Log Viewer

A modern, browser-based log viewer specifically designed for Harmony blockchain logs. This tool provides an intuitive interface for analyzing and filtering JSON-structured log files with advanced filtering capabilities and real-time search functionality.

## Features

### 🔍 **Advanced Filtering**
- **Log Level Filtering**: Filter by ERROR, WARN, INFO, DEBUG, etc.
- **Message Search**: Real-time text search within log messages
- **Module Filtering**: Filter by specific modules (e.g., `utils`, `consensus`)
- **Submodule Filtering**: Filter by submodules within modules
- **Shard Filtering**: Filter by specific shard IDs
- **Clear Filters**: One-click filter reset

### 📊 **Visual Log Analysis**
- **Color-coded Log Levels**: 
  - 🔴 Errors: Red background with bold text
  - 🟡 Warnings: Orange background with bold text
  - 🔵 Info/Debug: Standard styling
- **Interactive Table**: Click any log entry to view full JSON details
- **File Management**: Load and switch between multiple log files
- **Progress Tracking**: Real-time loading progress for large files

### 🎯 **Smart Parsing**
- **JSONL Support**: Handles one JSON object per line format
- **Pretty-printed JSON**: Supports multi-line formatted JSON objects
- **Automatic Format Detection**: Automatically detects and parses different JSON formats
- **Error Handling**: Graceful error handling with user-friendly messages

### 📱 **User Experience**
- **Responsive Design**: Works on desktop and mobile devices
- **Modal Details**: Click any log entry to see complete JSON structure
- **File List**: Sidebar showing loaded files with visual indicators
- **Loading Overlay**: Progress bar for large file processing

## Installation

### Prerequisites
- Modern web browser (Chrome, Firefox, Safari, Edge)
- No server setup required - runs entirely in the browser

### Quick Start
1. **Download the file**:
   ```bash
   wget https://raw.githubusercontent.com/harmony-one/HarmonyLogViewer/main/log_viewer.html
   ```

2. **Open in browser**:
   ```bash
   # Using Python (if available)
   python3 -m http.server 8000
   # Then open http://localhost:8000/log_viewer.html
   
   # Or simply double-click the file to open directly in browser
   ```

3. **Alternative: Clone the repository**:
   ```bash
   git clone https://github.com/harmony-one/HarmonyLogViewer.git
   cd HarmonyLogViewer
   # Open log_viewer.html in your browser
   ```

## Usage

### Loading Log Files
1. Click the **"Choose Files"** button
2. Select one or more log files (`.log`, `.txt`, `.jsonl`)
3. Files will be loaded and displayed in the sidebar
4. Click on any file in the sidebar to view its contents

### Filtering Logs
- **Level Filter**: Select specific log levels (ERROR, WARN, INFO, etc.)
- **Message Filter**: Type text to search within log messages
- **Module Filter**: Select specific modules to filter by
- **Submodule Filter**: Filter by submodules (updates based on selected module)
- **Shard Filter**: Filter by specific shard IDs
- **Clear Filters**: Reset all filters to show all logs

### Viewing Log Details
- Click on any log entry in the table
- A modal will open showing the complete JSON structure
- Click outside the modal or the × button to close

### File Management
- **Multiple Files**: Load multiple log files simultaneously
- **File Switching**: Click different files in the sidebar to switch between them
- **Visual Indicators**: Files with errors/warnings are highlighted

## Supported Log Formats

### JSONL Format (Recommended)
```
{"time":"2024-01-15T10:30:45Z","level":"info","message":"Node started","shardID":0,"caller":"/path/to/module.go:123"}
{"time":"2024-01-15T10:30:46Z","level":"error","message":"Connection failed","shardID":1,"caller":"/path/to/network.go:456"}
```

### Pretty-printed JSON Objects
```json
{
  "time": "2024-01-15T10:30:45Z",
  "level": "info",
  "message": "Node started",
  "shardID": 0,
  "caller": "/path/to/module.go:123"
}
{
  "time": "2024-01-15T10:30:46Z",
  "level": "error",
  "message": "Connection failed",
  "shardID": 1,
  "caller": "/path/to/network.go:456"
}
```

## Log Entry Structure

The viewer expects log entries with the following fields:

| Field | Type | Description | Example |
|-------|------|-------------|---------|
| `time` | string | Timestamp of the log entry | `"2024-01-15T10:30:45Z"` |
| `level` | string | Log level | `"error"`, `"warn"`, `"info"`, `"debug"` |
| `message` | string | Log message content | `"Node started successfully"` |
| `shardID` / `shard` | number/string | Shard identifier | `0`, `"shard-1"` |
| `caller` | string | Source file and line | `"/path/to/module.go:123"` |

## Browser Compatibility

- ✅ **Chrome** 80+
- ✅ **Firefox** 75+
- ✅ **Safari** 13+
- ✅ **Edge** 80+

## Performance

- **Large Files**: Handles files with millions of log entries
- **Progressive Loading**: Processes files in chunks to maintain responsiveness
- **Memory Efficient**: Streams data processing to avoid memory issues
- **Real-time Filtering**: Instant filter application without delays

## Troubleshooting

### Common Issues

**"Failed to load log file"**
- Ensure your log file contains valid JSON objects
- Check that each log entry is properly formatted
- Verify the file isn't corrupted

**"No JSON objects found"**
- Make sure your log file uses either JSONL or pretty-printed JSON format
- Check that the file isn't empty or contains only whitespace

**Slow performance with large files**
- The viewer processes files progressively
- Large files may take a few seconds to load
- Progress is shown in the loading overlay

**Filters not working**
- Ensure the log entries contain the expected fields
- Check that the field names match exactly (e.g., `shardID` vs `shard`)

## Contributing

Contributions are welcome! Please feel free to submit issues and pull requests.

### Development Setup
1. Clone the repository
2. Make your changes to `log_viewer.html`
3. Test with sample log files
4. Submit a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For issues, questions, or feature requests:
- Open an issue on GitHub
- Check existing issues for solutions
- Review the troubleshooting section above

---

**Made with ❤️ for the Harmony community** 