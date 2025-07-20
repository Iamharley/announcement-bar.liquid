# announcement-bar.liquid
<div class="announcement announcement-bar-index-only--{{ section.settings.show_announcement_home_only }}">
  <div class="announcement__wrapper">
    {%- if section.settings.announcement_link != blank -%}
      <a href="{{ section.settings.announcement_link }}" class="announcement__link">
    {%- endif -%}

    <div class="announcement__text" data-text="{{ section.settings.announcement_text | strip_html | handle }}">
      {{ section.settings.announcement_text | strip_html }}
    </div>

    {%- if section.settings.announcement_link != blank -%}
      </a>
    {%- endif -%}
  </div>
</div>

{% schema %}
{
  "name": "t:sections.header.settings.header_announcement_bar",
  "settings": [
    {
      "type": "checkbox",
      "id": "show_announcement_home_only",
      "label": "t:sections.header.settings.show_announcement_home_only.label"
    },
    {
      "type": "text",
      "id": "announcement_text",
      "label": "t:sections.header.settings.announcement_text.label",
      "default": "Free shipping and returns"
    },
    {
      "type": "url",
      "id": "announcement_link",
      "label": "t:sections.header.settings.announcement_link.label"
    }
  ]
}
{% endschema %}
