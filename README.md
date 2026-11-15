<p align="center"><img src="logo.png" width="120" alt="PrintBot"></p>

# PrintBot

**Ask your AI. Your printer prints.**

PrintBot is a hosted MCP server that lets Claude and other AI assistants print to the printer you already have at home or in the office. Ask for a grocery checklist, a worksheet, a recipe card or a meeting agenda, say "print it", and a clean page comes out a few seconds later, even when you asked from your phone.

- Website: [getprintbot.com](https://getprintbot.com/go/github)
- MCP endpoint: `https://getprintbot.com/mcp` (Streamable HTTP, OAuth sign-in)
- Official MCP Registry: `com.getprintbot/printbot`
- Free for 5 prints a month (up to 25 pages). PrintBot Plus is $7.99/month for 200 pages; PrintBot + TextBot is $9.99/month.

This repository holds the listing for PrintBot: the README, the registry file ([`server.json`](server.json)) and the logo. PrintBot itself is a hosted service, so there is nothing to install from here.

## 1. Connect your printer

1. Sign in at [getprintbot.com/setup](https://getprintbot.com/go/github?to=setup).
2. Download [PrintBot for Mac](https://getprintbot.com/go/github?to=mac) (free, signed and notarized), open it and click **Link**.
3. Make sure your printer works from that Mac (System Settings → Printers & Scanners). Keep PrintBot open and the Mac awake.

Windows is coming. You can [join the waitlist](https://getprintbot.com/go/github?to=setup) for an email when it is ready.

## 2. Connect your AI

**Claude** (claude.ai, desktop and the iPhone/iPad app): find PrintBot in the Claude connector directory, or add a custom connector with the URL `https://getprintbot.com/mcp`. Sign in when asked.

**Claude Code:**

```bash
claude mcp add --transport http printbot https://getprintbot.com/mcp
```

**Cursor** (`~/.cursor/mcp.json`) and other MCP clients that support remote servers with OAuth:

```json
{
  "mcpServers": {
    "printbot": { "url": "https://getprintbot.com/mcp" }
  }
}
```

**ChatGPT:** the ChatGPT app prints through email. Copy your private print address from the ChatGPT tab on [setup](https://getprintbot.com/go/github?to=setup), and ChatGPT (with Gmail connected) emails the document to your printer. PrintBot replies by email with the result, so ask ChatGPT to check your Gmail for PrintBot's reply.

## Tools

| Tool | What it does |
|---|---|
| `print_document` | Typesets Markdown into a clean US Letter PDF and prints it. Supports headings, lists, checkboxes, quotes and simple tables. `dry_run` reports the page count without printing. |
| `print_pdf` | Prints an existing PDF from a public https URL or base64 bytes. |
| `list_printers` | Lists your connected printers and your default. |
| `get_printer_status` | Whether your printer and its computer are online. |
| `get_print_job_status` | The state of a print job. "done" means the computer handed the job to the printer. |
| `list_recent_print_jobs` | Your most recent print jobs. |
| `setup_status` | Your setup, monthly usage and limits, and the next step. |
| `get_setup_help` | Computer choice, download and linking steps. |
| `printer_setup_guide` | The maker's setup link and general Wi-Fi steps for a printer brand and model. |

## Example prompts

- "Make a grocery checklist for tacos for six and print it."
- "Print a one-page agenda for tomorrow's 10am team meeting."
- "Turn this recipe into a recipe card and print two copies."
- "Make a times-tables worksheet for a third grader and print it."

## Privacy and safety

- PrintBot prints only when you ask. Every job shows up in your recent prints.
- Print files are deleted within a day.
- PrintBot receives only the content and print requests your assistant sends, not your chat history.
- [Privacy](https://getprintbot.com/privacy) · [Terms](https://getprintbot.com/terms) · [Support](https://getprintbot.com/support)

## Contact

- Help: support@getprintbot.com
- Security reports: security@getprintbot.com

PrintBot is made by Wander App Inc.
