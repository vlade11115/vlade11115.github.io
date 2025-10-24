# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a GitHub Pages site hosted at `otherstaff.xyz` that serves static HTML pages. The repository contains:
- A placeholder page at `/docs/index.html`
- An interactive map application at `/docs/inzhur-map.html` showing inzhur REIT locations

## Architecture

### Site Structure
- **docs/**: GitHub Pages source directory
  - **index.html**: Simple HTML placeholder
  - **inzhur-map.html**: Standalone Leaflet.js map application
  - **CNAME**: Domain configuration for `otherstaff.xyz`

### Map Application (`inzhur-map.html`)
- Self-contained single-file application with no external dependencies except CDN resources
- Uses Leaflet.js 1.9.4 for interactive mapping
- Data structure: Array of location objects embedded in `<script>` tag (lines 156-248)
- Each location has: id, name, category, lat/lng coordinates, description, details, and color
- Features:
  - Interactive map with custom colored markers
  - Sidebar list of all locations (collapsible on mobile)
  - Click locations in sidebar to zoom/center on map
  - Reset view control button
  - Responsive design with mobile support



### Deploying Changes
This repository uses GitHub Pages serving from the `/docs` directory. Changes pushed to the `main` branch are automatically deployed.

### Adding New Locations to the Map
Edit the `locations` array in `docs/inzhur-map.html` (starting at line 156). Each location object requires:
- `id`: Unique integer identifier
- `name`: Location name (e.g., "Супермаркет «Сільпо»")
- `category`: Type of location (e.g., "Супермаркет", "Ресторан")
- `lat`, `lng`: GPS coordinates (decimal degrees)
- `description`: Brief description of the location
- `details`: Additional info (opening date, square footage)
- `color`: Hex color for map marker (e.g., "#27ae60" for green)

## Important Notes

- All content is in Ukrainian language
- The map is centered on Kyiv area (default view: [50.4501, 30.5234])
- CDN dependencies: Leaflet.js CSS/JS from unpkg.com
- No build process required - direct HTML/CSS/JavaScript