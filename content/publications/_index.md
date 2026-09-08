---
title: Publications
cms_exclude: true
type: landing

sections:
  - block: collection
    id: papers
    content:
      title: Publications
      text: ''
      count: 500
      filters:
        folders:
          - publications
        exclude_featured: false
        sort_by: 'date'
        sort_ascending: true
    design:
      view: citation

  - block: collection
    id: conferences
    content:
      title: Conference
      text: ''
      count: 500
      filters:
        folders:
          - conferences
        exclude_featured: false
        sort_by: 'date'
        sort_ascending: true
    design:
      view: citation
---
