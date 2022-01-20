---
aliases: 
created: 2021-12-08, 8:51:59 am (Wednesday, December 8th)
updated: 2022-01-10, 12:25:02 pm (Monday, January 10th)
---
#digitone #sound-design

# Envelope Notes

Notes here are derived from using an UNTITLED patch w/ the following tweaks:
- SYN 2:
    - Level: 127

Here's a rough guestimate to what the values in the table below quantify to:
- Instant: 0ms
- Quick: 0ms < x <= 200ms
- Medium: 200ms < x <= 500ms
- Slow: 500ms < x <= 1ms

<table>
  <thead>
    <tr>
      <td>Perceived length</td>
      <td>Value</td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Instant</td>
      <td>0</td>
    </tr>
    <tr>
      <td>Quick</td>
      <td>0 lt x gte 25</td>
    </tr>
     <tr>
      <td>Medium</td>
      <td>25 lt x lt 50</td>
    </tr>
     <tr>
      <td>Slow</td>
      <td>50 gte x</td>
    </tr>
  </tbody>
</table>

## Related
- [[Music/Digitone/EditExistingSound]]
- [[Music/Digitone/MakeNewSound]]