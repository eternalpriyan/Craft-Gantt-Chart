# Craft Gantt

A web-based Gantt chart viewer for Craft Docs Collections. Point the tool at a Craft collection containing project tasks, and it renders an interactive timeline with dependencies. Changes made in the chart (drag to reschedule, resize duration) sync back to Craft via API.

## Features

- **Interactive Gantt Chart** - Drag tasks to reschedule, resize to change duration
- **Craft API Integration** - Connect to any Craft collection via Multi-Document API
- **Auto-Sync** - Changes automatically sync back to your Craft collection
- **Multiple Views** - Day, Week, and Month view modes
- **Dark/Light Theme** - Matches Craft's aesthetic
- **Status Colors** - Visual indicators for Not Started, In Progress, Done, and Blocked
- **Dependencies** - Visualize task dependencies with arrows
- **Progress Tracking** - See and update task completion percentage
- **Keyboard Shortcuts** - Quick navigation and controls

## Getting Started

### 1. Create a Craft API Connection

1. Open your Craft document containing a collection
2. Go to **Share** → **API Access**
3. Create a Multi-Document API connection
4. Copy the API URL (e.g., `https://connect.craft.do/links/{linkId}/api/v1`)

### 2. Configure Your Collection

Your Craft collection should have these properties:

| Property | Type | Required | Purpose |
|----------|------|----------|---------|
| Title | title | Yes | Task name (Gantt bar label) |
| Start Date | date | Yes | Left edge of bar |
| End Date | date | Yes | Right edge of bar |
| Dependencies | text | No | Comma-separated task titles |
| Status | select | No | Color coding (Not Started, In Progress, Done, Blocked) |
| Progress | number | No | Percentage complete (0-100) |
| Assignee | text | No | Optional grouping/filtering |

### 3. Connect to Craft Gantt

1. Open [Craft Gantt](https://eternalpriyan.github.io/craft-gantt/)
2. Click **Connect to Craft**
3. Paste your API URL
4. Select your collection from the dropdown
5. Verify property mappings (auto-detected)
6. Click **Save**

## Usage

### Navigating the Chart

- **Scroll** horizontally to move through the timeline
- **Click** on a task bar to view details
- **Drag** a task bar to reschedule it
- **Resize** bar edges to change duration

### View Modes

| Mode | Description |
|------|-------------|
| Day | Shows individual days |
| Week | Shows weeks (default) |
| Month | Shows months |

### Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `T` | Scroll to today |
| `D` | Day view |
| `W` | Week view |
| `M` | Month view |
| `R` | Refresh data |
| `,` | Open settings |
| `Esc` | Close modal/popup |
| `←` / `→` | Navigate timeline |

## Use Cases

- **Content Calendars** - Blog posts, video releases, social media
- **Course Planning** - Curriculum development, training programs
- **Event Planning** - Milestones, deadlines, vendor coordination
- **Client Timelines** - Shareable project schedules
- **Personal Projects** - Home renovation, wedding, moving

## Technical Details

### Stack

| Component | Choice |
|-----------|--------|
| Rendering | [Frappe Gantt](https://frappe.io/gantt) |
| Frontend | Single HTML file (vanilla JS) |
| Styling | CSS custom properties |
| API | Craft Multi-Document API |

### File Structure

```
craft-gantt/
├── index.html      # Single-file app (HTML + CSS + JS)
├── README.md       # This file
└── test-data.json  # Sample data for development
```

### Browser Support

- Chrome (recommended)
- Firefox
- Safari
- Edge

### Data Storage

Settings are stored in `localStorage`:
- API URL
- Selected collection
- Property mappings
- Theme preference
- View mode

## Development

### Local Development

1. Clone the repository
2. Open `index.html` in a browser
3. Use `test-data.json` as reference for expected data format

### Testing with Sample Data

The `test-data.json` file contains sample project tasks demonstrating:
- Sequential dependencies
- Parallel tasks
- Multiple dependencies
- Various statuses and progress levels

## Related Tools

- [Craft Timeblock](https://eternalpriyan.github.io/craft-timeblock/) - Time blocking from Craft
- [Craft Kanban](https://eternalpriyan.github.io/craft-kanban/) - Kanban board for Craft

## License

MIT
