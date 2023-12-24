# Davinch Project Structure

## Overview

This repository offers a suggested directory structure for centralized material management in **DaVinci Resolve**. It also provides shell scripts to create this directory setup. The aim is to facilitate project organization and promote an efficient workflow.

## Installation and Notes

Clone this repository and set your path to the `bin` directory to make the included commands available. We recommend checking for security and dependencies to ensure compatibility with your environment.

```bash
git clone https://github.com/atu4403/davinch-project-structure.git
cd davinch-project-structure
export PATH=$(pwd)/bin:$PATH
```

This setup is temporary. To use the commands permanently, add them to your shell configuration file (like `.bashrc` or `.zshrc`).

## Commands

- `init_davinch_project`: initializes the Davinch workspace and creates a sharedMaterials directory (SharedMaterials) and a project directory (Projects).
- `new_davinch_project`: creates a new project and generates the necessary directory structure in `Projects`.


### `init_davinch_project`

This command sets up the initial environment for Davinch projects. It creates a main directory (named 'Davinch' by default or a custom name provided by the user) and organizes shared resources and project spaces.

#### Created Structure

- `Davinch/` (or custom name): The main directory containing all project-related materials.
  - `SharedMaterials/`: A directory for common assets used across multiple projects.
    - `Music/`: Contains music files, divided into subcategories.
      - `Favorites/`
      - `RoyaltyFreeMusic/`
      - `PaidMusic/`
    - `SoundEffects/`: Stores various sound effects.
      - `Favorites/`
      - `NaturalSounds/`
      - `SyntheticSounds/`
      - `UniqueSoundEffects/`
    - `Image/`: Holds image files like photographs, illustrations, and background images.
      - `Favorites/`
      - `Photographs/`
      - `Illustrations/`
      - `BackgroundImages/`
    - `Video/`: Contains video clips and stock videos.
      - `Favorites/`
      - `FreeStockVideos/`
      - `PaidStockVideos/`
    - `VideoEffects/`: Stores video effects like transitions and filters.
      - `Favorites/`
      - `Transitions/`
      - `Filters/`
      - `Templates/`
  - `Projects/`: A directory intended for individual project folders.

### `new_davinch_project`

Used for creating a new, individual project within the `Projects/` directory of the Davinch workspace. Each project folder contains organized subdirectories for project-specific materials.

#### Created Structure for Each Project

- `ProjectName/`: The main folder for a specific project, with the following structure:
  - `RawMaterials/`: Contains all the raw files and assets specific to the project.
    - `Video/`: Holds main and supplementary video footage.
      - `MainFootage/`
      - `SupplementaryFootage/`
    - `Audio/`: Stores audio files like narrations and on-site recordings.
      - `Narration/`
      - `OnSiteAudio/`
    - `Image/`: Directory for project-specific images and slides created in Keynote.
      - `ProjectSpecificImages/`
      - `KeynoteSlides/`
  - `Exports/`: This is where all exported versions of the project are saved.
    - Example files: `Draft_YYYY-MM-DD.mp4`, `PreRelease_YYYY-MM-DD.mp4`, `Final_YYYY-MM-DD.mp4`
  - `SupportingMaterials/`: Contains additional supporting documents like storyboards, shot lists, and scripts.
    - `Storyboard.pdf`
    - `ShotList.xlsx`
    - `Script.md`

## Usage

- Run `init_davinch_project` to create the initial Davinch workspace with shared resources.
- Use `new_davinch_project [ProjectName]` to create a new project with the specific structure under the `Projects/` directory.
