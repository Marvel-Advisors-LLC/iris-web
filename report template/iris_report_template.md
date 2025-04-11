
# Incident Report - {{ case.name }}

**Date Created:** {{ case.open_date }}  
**Reported by:** {{ case.opened_by }}  
**Severity:** {{ case.severity }}  
**Customer:** {{ case.for_customer }}

---

## 📝 Description

{{ case.description }}

---

## 🚨 Alerts

{% for alert in case.alerts %}
### Alert {{ loop.index }}

- **Title**: {{ alert.title }}
- **Agent**: {{ alert.agent_name }}
- **Log**:  
```
{{ alert.full_log }}
```

{% endfor %}

---

## 📄 Notes

{% for note in case.notes %}
### {{ note.note_title }}

{{ note.note_content }}

_Added on {{ note.note_creationdate }}_
{% endfor %}

---

## 🧪 IOCs

{% for ioc in case.iocs %}
- **Value**: {{ ioc.ioc_value }}  
  **Type**: {{ ioc.ioc_type }}  
  **Description**: {{ ioc.ioc_description }}
{% endfor %}

---

## 📅 Timeline

{% for event in case.timeline %}
### {{ event.event_title }}

- **Date**: {{ event.event_date }}
- **Source**: {{ event.event_source }}
- **Details**: {{ event.event_content }}

{% endfor %}
