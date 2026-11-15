# OpenGOAL Mod List Template

This repo serves as a template for anyone wishing to host/maintain an OpenGOAL mod list.

## Overview

The OpenGOAL launcher expects a json file that lists all of the available releases for each mod, so that it doesn't have to poll GitHub for this information every time.

To simplify the maintenance of json file, you just need to add details about your mod(s) to the `scripts/config.yaml` file. From there, a GitHub workflow will run every 30 minutes, and fetch the necessary information about each mod to generate `mods.json` in the expected format.

## Setup

- Click the green "Use this template" button in the top right to create your own repo from this template
- In your repo, edit the `scripts/config.yaml` file and fill out the information about your mod list and mod(s):
    - Set your mod list `name` at the top
    - Add your mod(s) under `mods`, following the format in the examples provided (without the comments, i.e. no `#`s)

## Mod List Update

- Once you've followed the above setup, your list should auto-update every 30 minutes via the `Update Mod Source` GitHub Action
    - You can go to the Actions tab and manually kick off this worflow if you have an update and don't want to wait for the scheduled job
- Once the GitHub Action has completed, your `mods.json` file should be updated
- If you're having issues, go to the Actions tab and review the logs for the latest `Update Mod Source` run to troubleshoot what went wrong.

## Adding Mod List to Launcher

IMPORTANT: be sure to use the *raw* URL when adding this file to the OpenGOAL Launcher, e.g. `https://github.com/your-username/ModListTemplate/raw/refs/heads/main/mods.json`
