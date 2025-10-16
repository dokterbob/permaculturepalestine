# Claude Code Documentation for Permaculture Palestine Website

## Overview
This document provides guidance for Claude Code (AI assistant) on how to maintain and update the Permaculture Palestine website by gathering information from the PePa Telegram group.

## Telegram Group Structure

### Main Group
- **Chat ID:** 2994808408
- **Name:** PePa
- **Type:** Supergroup
- **Members:** 267+ (as of October 2025)

### Key Topic Areas (within main group)
Messages are organized by topic threads. Key topics include:
- **Social Media/Outreach** (ID: 578) - Announcements, flyers, promotional materials
- **Statement** (ID: 835) - Italian language discussions
- **Seeds** (ID: 2) - Seeds & food sovereignty work
- **Introductions** (ID: 67) - Member introductions
- **General** (ID: 1537) - General discussions and event planning
- **Funding/Volunteers** - Direct support initiatives

## Common Tasks

### 1. Updating Event Information

**Steps:**
1. Search for recent messages about upcoming events:
   ```
   mcp__telegram-mcp__search_messages with:
   - chat_id: 2994808408
   - query: "register" or "zoom.us" or specific date
   - limit: 50
   ```

2. Look for key information:
   - Event title and description
   - Date and time (in multiple timezones: Palestine Time, CET, UK Time)
   - Registration/Zoom links
   - Special features (translation services, speakers, etc.)

3. Check the Social Media topic (ID: 578) for finalized announcements

### 2. Finding Registration Links

**Common patterns in messages:**
- Zoom registration: `https://zoom.us/meeting/register/[CODE]`
- Time format: "@ 19:30h Palestine Time / 18:30h CET / 17:30 UK Time"
- Look for messages from ~alfred (primary organizer)

### 3. Gathering Event Details

**Key message IDs to check:**
- Recent messages (last 7 days) via `list_messages` with `from_date` parameter
- Search for event-specific terms: event name, date, "registration"
- Check message context around found messages using `get_message_context`

### 4. Identifying Partner Organizations

Search for:
- Organization introductions in Introductions topic (ID: 67)
- Links to external websites (e.g., apnature.org, permaculture.org.uk)
- Announcements about collaborations

## Website Update Workflow

### index.html Structure

**Sections to maintain:**
1. **Hero Section** - Main call-to-action and tagline
2. **About Section** - Member count (update regularly)
3. **Statement Section** - Core values and petition link
4. **Events Section:**
   - **Upcoming Events** - Future events with registration info
   - **Recent Events** - Past events with recordings/summaries
5. **Working Groups** - Active subgroups and their focus
6. **Partners** - Featured organizations and projects
7. **Contact** - Telegram, email list, social media links

### Event Card Template

```html
<div class="event-card">
    <h3>[Event Title]</h3>
    <p class="event-date">[Date] @ [Times in multiple timezones]</p>

    <p>[Event description]</p>

    <p>[Additional context, speakers, special features]</p>

    <p><strong>Registration:</strong> <a href="[LINK]" target="_blank" rel="noopener">[LINK]</a></p>
</div>
```

### Moving Events from Upcoming to Recent

When an event passes:
1. Move from "Upcoming Events" to "Recent Events"
2. Update language from future tense to past tense
3. Replace registration link with recording link (when available)
4. Add "will be recorded" → "recording available"

## Key Contacts & References

**Primary Organizers:**
- ~alfred - Main coordinator, frequent poster
- Sasha - Social media coordination
- Annamaria - Italian translation and coordination
- Jorge B - Spanish/German language coordination

**Important Links:**
- Change.org petition: https://www.change.org/permaculturepalestine or https://chng.it/mM5wR94Cq6
- Telegram group: https://t.me/+3ejhkzOd4l03NjM0
- Email list: permaculture-palestine-subscribe@lists.riseup.net
- Instagram: @permaculturepalestine
- Facebook: Permaculture & Palestine

## Search Tips

**Finding event information:**
1. Search for date: "October 23", "23rd"
2. Search for registration: "zoom.us", "register", "registration"
3. Search for time: "19:00", "CET"
4. Check topic 578 for finalized social media announcements

**Finding partner information:**
1. Search for URLs: ".org", "http"
2. Check introductions topic (ID: 67)
3. Look for "partnership", "collaboration", "working with"

## Multilingual Content

The group operates in multiple languages:
- English (primary)
- العربية (Arabic)
- Español (Spanish)
- Français (French)
- Italiano (Italian)
- Ελληνικά (Greek)

Event announcements are often translated into multiple languages. Look for translated versions in the same message thread or nearby messages.

## Data Freshness

- Always check messages from the last 7-14 days for most current information
- Member count changes regularly - search for recent references
- Event details may be updated multiple times before finalization
- Registration links are typically finalized 3-7 days before events

## Common Issues

**Missing registration link:**
- Event may still be in planning
- Check if it's internal-only (no public registration)
- Social media group may be preparing materials
- Follow up in a few days

**Multiple conflicting times:**
- Later messages override earlier ones
- Check message timestamps
- Verify with context from surrounding messages
- Italian topic (835) sometimes has clarifications

**Outdated information:**
- Always prioritize most recent messages
- Check for corrections or updates in message threads
- Look for "update:", "correction:", or "changed to:"

## Automation Suggestions

For future improvements, consider:
1. Daily check of PePa group for new announcements
2. Automated detection of Zoom registration links
3. Partner organization monitoring via website links
4. Member count tracking over time
5. Event calendar synchronization

## Critical Verification Steps

**ALWAYS verify before adding to website:**

1. **Double-check dates and days of week:**
   - Use date verification: `date -j -f "%Y-%m-%d" "YYYY-MM-DD" +"%A"`
   - Don't assume - verify the actual day matches what's stated

2. **Verify all URLs before adding:**
   - Registration links (zoom.us)
   - External organization websites
   - Social media profiles
   - Email addresses

3. **Confirm times across timezones:**
   - Check that timezone conversions are correct
   - Typical pattern: Palestine Time (EET) = CET + 1 hour = UK Time + 2 hours
   - Example: 20:00 Palestine = 19:00 CET = 18:00 UK

4. **Cross-reference multiple messages:**
   - Look for the most recent announcement
   - Check for corrections or updates
   - Verify information appears in multiple messages

5. **When information conflicts:**
   - Prioritize most recent messages
   - Check the Social Media topic (578) for finalized versions
   - Look for explicit corrections ("update:", "correction:", "changed to:")

## Last Updated
October 16, 2025
