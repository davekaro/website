---
layout: 
---

/downloads/:version/:file https://github.com/yarnpkg/yarn/releases/download/v:version/:file

# Nice short URLs to download the latest release
/latest.tar.gz     https://github.com/yarnpkg/yarn/releases/download/v{{site.latest_version}}/yarn-v{{site.latest_version}}.tar.gz      302
/latest.tar.gz.asc https://github.com/yarnpkg/yarn/releases/download/v{{site.latest_version}}/yarn-v{{site.latest_version}}.tar.gz.asc  302
/latest.msi        https://github.com/yarnpkg/yarn/releases/download/v{{site.latest_version}}/yarn-{{site.latest_version}}.msi          302
/latest.deb        https://github.com/yarnpkg/yarn/releases/download/v{{site.latest_version}}/yarn_{{site.latest_version}}_all.deb      302
/latest.rpm        https://github.com/yarnpkg/yarn/releases/download/v{{site.latest_version}}/yarn-{{site.latest_version}}-1.noarch.rpm 302

# Nice short URLs for latest RC
# If Netlify supported regular expressions in their rewrite rules, these could
# simply be a part of the rules above. Alas, they don't support it :(
/latest-rc.tar.gz     https://github.com/yarnpkg/yarn/releases/download/v{{site.latest_rc_version}}/yarn-v{{site.latest_rc_version}}.tar.gz      302
/latest-rc.tar.gz.asc https://github.com/yarnpkg/yarn/releases/download/v{{site.latest_rc_version}}/yarn-v{{site.latest_rc_version}}.tar.gz.asc  302
/latest-rc.msi        https://github.com/yarnpkg/yarn/releases/download/v{{site.latest_rc_version}}/yarn-{{site.latest_rc_version}}.msi          302
/latest-rc.deb        https://github.com/yarnpkg/yarn/releases/download/v{{site.latest_rc_version}}/yarn_{{site.latest_rc_version}}_all.deb      302
/latest-rc.rpm        https://github.com/yarnpkg/yarn/releases/download/v{{site.latest_rc_version}}/yarn-{{site.latest_rc_version}}-1.noarch.rpm 302

/en  /  302

{% for language in site.data.languages %}
  {% if language.enabled %}
    {% if language.tag != "en" %}
      {% for accept_language in language.accept_languages %}
/  /{{language.tag}}  302  Language={{accept_language}}
      {% endfor %}
    {% endif %}

/{{language.tag}}/docs/install_ci   /{{language.tag}}/docs/install-ci  302
  {% endif %}
{% endfor %}
