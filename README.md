
## Overview

The **SVG Publish SharePoint Web Part** is an interactive web part that allows you to display and interact with SVG diagrams exported from Microsoft Visio directly within SharePoint Online. This web part provides rich interactivity features including pan, zoom, hyperlinks, tooltips, layers, shape selection, and more.

The web part runs entirely inside your SharePoint tenant to display the diagram. It does not call, depend on, or send your data to any external services or third-party servers. This is an explicit privacy feature so your diagram content remains within your tenant.
<a href="https://appsource.microsoft.com/en-us/product/office/WA200009144" target="_blank" rel="noopener">
<img src="https://unmanagedvisio.com/wp-content/uploads/2025/09/image-1757072019258.png"></img>
</a>

https://appsource.microsoft.com/en-us/product/office/WA200009144

[notification type=warning]The web part is designed to work within the constraints of SharePoint Online, which means that **custom scripts are disabled** in the web part settings, and you will not be able to use any custom JavaScript code in the web part in the custom content. This is done on purpose to allow the web part to run in the "custom scripts disabled" environment. The formatting and markdown is supported[/notification]

[![SVG Publish web part screenshot](https://unmanagedvisio.com/wp-content/uploads/2025/08/main.png)](https://unmanagedvisio.com/wp-content/uploads/2025/08/main.png)

## Table of Contents

1. [Installation and Setup](#installation-and-setup)
2. [Basic Configuration](#basic-configuration)
3. [Property Panel Groups](#property-panel-groups)
4. [Usage Examples](#usage-examples)
5. [Troubleshooting](#troubleshooting)

## Installation and Setup

### Prerequisites

- SharePoint Online environment
- SVG files exported from Microsoft Visio using the SVG Publish tool
- Appropriate permissions to add web parts to SharePoint pages

### Adding the Web Part

1. Edit your SharePoint page
2. Click the "+" icon to add a new web part
3. Search for "SVG Publish" or find it in the web part gallery
4. Add the web part to your page

![file](https://unmanagedvisio.com/wp-content/uploads/2025/08/image-1755598446038.png)

## Basic Configuration

### Essential Settings

#### 1. Source File Configuration

- **SVG File**: Select the SVG file exported from Visio
  - Use the "Browse..." button to select from SharePoint document libraries
  - Supports files stored in SharePoint Online or OneDrive for Business
  - File must be accessible to users who will view the web part

#### 2. Display Settings

- **Diagram Width**: Set the width of the diagram (e.g., "800px", "100%")
- **Diagram Height**: Set the height of the diagram (e.g., "600px", "auto")
- **Saved View**: Save and restore a specific view (zoom level and position) for the diagram
- **Pan & Zoom Controls**: Enable/disable user interaction with the diagram
  - Option to require modifier keys (Ctrl/Shift) for zoom to prevent accidental zooming
  - Option to require two-finger touch gestures for better mobile experience

## Property Panel Groups

The web part organizes settings into logical groups for easy configuration:

### 1. Source File Group

- **SVG File**: Select the SVG file exported from Visio using file picker

For most options to work you should select an SVG file that was published using the SVGPublish add-in. This web part is a "companion" web part for it. If you select just a random SVG file, only basic appearance options will work.

![file](https://unmanagedvisio.com/wp-content/uploads/2025/08/image-1755598565630.png)

![file](https://unmanagedvisio.com/wp-content/uploads/2025/08/image-1755598535266.png)

### 2. Appearance Group

![file](https://unmanagedvisio.com/wp-content/uploads/2025/08/image-1755598616884.png)

- **Enable Pan**: Allow users to pan around the diagram
- **Enable Zoom**: Allow users to zoom in/out
  - **Require Ctrl key for zoom**: When enabled, users must hold Ctrl while scrolling to zoom (prevents accidental zooming)
  - **Require Shift key for zoom**: When enabled, users must hold Shift while scrolling to zoom (prevents accidental zooming)
- **Require two fingers for touch gestures**: When enabled, single-finger touch gestures are disabled, requiring two fingers for pan/zoom operations (better for mobile/tablet experiences)
- **Diagram Width**: Set the width of the diagram (e.g., "800px", "100%")
- **Diagram Height**: Set the height of the diagram (e.g., "600px", "auto")

### 3. Header Group

![file](https://unmanagedvisio.com/wp-content/uploads/2025/08/image-1755598825569.png)

- **Enable Header**: Show/hide the diagram header
- **Breadcrumb**: Show navigation breadcrumbs for multi-page diagrams (when header enabled)
- **Copy Link Button**: Enable copy hash link functionality (when header enabled)
- **Fullscreen Button**: Enable fullscreen mode button (when header enabled)
- **Custom Feedback URL**: Set custom feedback URL with {{URL}} placeholder (when copy link enabled)

### 4. Highlight & Selection Group

![file](https://unmanagedvisio.com/wp-content/uploads/2025/08/image-1755598953999.png)

- **Enable Highlight**: Enable hover highlighting effects
- **Enable Selection**: Allow selecting shapes
- **Auto-Show Sidebar on Selection**: Automatically open sidebar when shapes are selected
- **Hover Color**: Color used when hovering over shapes <span style="display:inline-block;width:12px;height:12px;background-color:rgba(255, 255, 0, 0.3);border:1px solid #ccc;vertical-align:middle;margin-left:4px;"></span>
- **Hyperlink Hover Color**: Color used when hovering over hyperlinks <span style="display:inline-block;width:12px;height:12px;background-color:rgba(0, 0, 255, 0.3);border:1px solid #ccc;vertical-align:middle;margin-left:4px;"></span>
- **Selection Color**: Color used when shapes are selected <span style="display:inline-block;width:12px;height:12px;background-color:rgba(255, 255, 0, 0.8);border:1px solid #ccc;vertical-align:middle;margin-left:4px;"></span>
- **Highlight & Selection Mode**: How highlighting appears ("normal", "lighten", "darken")
- **Enable Dilate**: Enable outline dilation effect
- **Dilate Size**: Size of the selection outline dilation (when dilate enabled)
- **Enable Blur**: Enable blur effect
- **Blur Amount**: Amount of blur effect (when blur enabled)
- **Use Box Selection**: Use simple rectangle selection style

### 5. Previous/Next Highlight Group

Controls highlighting of connected shapes:

![file](https://unmanagedvisio.com/wp-content/uploads/2025/08/image-1755599091361.png)

- **Enable Previous/Next Shape Colors**: Highlight connected shapes
- **Enable Previous/Next Connection Colors**: Highlight connections
- **Previous Shape Color**: Color for previous shapes <span style="display:inline-block;width:12px;height:12px;background-color:rgba(160, 255, 255, 0.8);border:1px solid #ccc;vertical-align:middle;margin-left:4px;"></span>
- **Next Shape Color**: Color for next shapes <span style="display:inline-block;width:12px;height:12px;background-color:rgba(255, 160, 255, 0.8);border:1px solid #ccc;vertical-align:middle;margin-left:4px;"></span>
- **Previous Connection Color**: Color for previous connections <span style="display:inline-block;width:12px;height:12px;background-color:rgba(255, 0, 0, 1.0);border:1px solid #ccc;vertical-align:middle;margin-left:4px;"></span>
- **Next Connection Color**: Color for next connections <span style="display:inline-block;width:12px;height:12px;background-color:rgba(255, 0, 0, 1.0);border:1px solid #ccc;vertical-align:middle;margin-left:4px;"></span>

### 6. Hyperlinks Group

- **Enable Follow Hyperlinks**: Allow clicking on hyperlinks in shapes
- **Open in New Window**: Control how hyperlinks open
- **Rewrite Visio Hyperlinks**: Convert hyperlinks to Visio files (.vsdx or .vsd) to SVG files with the same name (.svg). Can be useful when publishing a bunch of inter-linked diagrams, which is the case for many SvgPublish users.
- **Rewrite Office Hyperlinks**: Always use web-version for the office file links (open in the web-apps, i.e. automatically append ?web=1 if not present)

### 7. Tooltips Group

![file](https://unmanagedvisio.com/wp-content/uploads/2025/08/image-1755599355672.png)

- **Enable Tooltips**: Show tooltips on hover or click
- **Use Mouse Position**: Position tooltip at mouse cursor
- **Allow Tooltip Interaction**: Enable interaction with tooltip content
- **Suppress Tooltips on Mobile**: Disable tooltips on touch devices
- **Tooltip Theme**: Visual style ("dark", "light", "light-border", "translucent")
- **Tooltip Trigger**: How to trigger tooltips ("mouseenter", "click", "mouseenter click")
- **Tooltip Placement**: Position relative to cursor/shape
- **Enable Tooltip Delays**: Enable show/hide delays
- **Show/Hide Delays**: Timing for tooltip appearance/disappearance

### 8. Custom Content Group

You can specify your content for tooltips, sidebar, or shape overlays.
The custom content can contain markdown and reference shape properties.

For the future details on templates, please refer the article below. In the web part, the custom content works exactly the same way.
https://unmanagedvisio.com/using-custom-templates-in-svgpublish/

![file](https://unmanagedvisio.com/wp-content/uploads/2025/09/image-1756802733296.png)

- **Enable Custom Tooltip Content**: Use custom Markdown content for tooltips
- **Tooltip Content Template**: Custom Markdown content (when enabled)
- **Enable Custom Overlay Content**: Add custom content with Markdown support
- **Overlay Content Template**: Custom Markdown content to display (when enabled)
- **Enable Custom Sidebar Content**: Add custom content with Markdown support
- **Sidebar Content Template**: Custom Markdown content to display (when enabled)

### 9. Sidebar Group

![file](https://unmanagedvisio.com/wp-content/uploads/2025/08/image-1755599844086.png)

- **Enable Sidebar**: Show/hide the information sidebar
- **Sidebar Size**: Size and position options ("Small", "Medium", "Large", "Custom", etc.)
- **Sidebar Width**: Custom width setting (when custom size selected)
- **Show Sidebar Title**: Display title in sidebar
- **Show Shape Properties**: Display shape properties in sidebar
- **Property Filter**: Select specific properties to show
- **Show Shape Links**: Display hyperlinks in sidebar
- **Enable Pages Navigation**: Enable multi-page navigation controls
- **Page Search**: Enable page search functionality (when pages enabled)
- **Sort Pages Alphabetically**: Sort pages alphabetically (when pages enabled)
- **Enable Shape Search**: Enable shape search functionality
- **Property Search Filter**: Enable property-based search filtering (when search enabled)
- **Show Layers**: Display layer controls in sidebar
- **Layer Search**: Enable layer search (when layers enabled)
- **Sort Layers Alphabetically**: Sort layers alphabetically (when layers enabled)
- **Show All/Hide All Buttons**: Layer visibility toggle buttons (when layers enabled)
