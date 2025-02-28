---
title: Home
slug: /
sections:
  - type: GenericSection
    title:
      text: Anna Dupree
      color: text-dark
      type: TitleBlock
    subtitle: Statistics Enthusiast
    text: >
      Senior UCLA student of Statistics and Applied Mathematics. Willing to draw
      anything!
    actions:
      - label: Resume
        altText: resume
        url: /resume
        showIcon: false
        icon: arrowRight
        iconPosition: right
        style: secondary
        elementId: ''
        type: Button
    media:
      url: /images/42d979481322a289-sticker.png.png
      altText: Call me Memoji
      elementId: ''
      type: ImageBlock
      styles:
        self:
          padding:
            - pl-2
            - pr-2
    badge:
      label: This is a badge
      color: text-primary
      type: Badge
    elementId: ''
    colors: bg-light-fg-dark
    styles:
      self:
        alignItems: center
        flexDirection: row
        padding:
          - pt-16
          - pl-16
          - pb-16
          - pr-16
  - type: FeaturedItemsSection
    title:
      text: EXPERIENCE
      color: text-dark
      styles:
        self:
          textAlign: center
          fontWeight: 400
      type: TitleBlock
    subtitle: ''
    items:
      - title: Technical Writing Consultant
        subtitle: Jan 2025 - Present
        text: >
          Collaborated with several academics in the writing of a scientific
          article.
        image:
          altText: Featured icon two
          elementId: ''
          type: ImageBlock
        actions: []
        colors: bg-neutralAlt-fg-dark
        styles:
          self:
            padding:
              - pt-8
              - pl-8
              - pb-8
              - pr-8
            borderRadius: x-large
            flexDirection: row
            textAlign: left
            justifyContent: center
        type: FeaturedItem
      - type: FeaturedItem
        title: Software Engineering Intern
        subtitle: June 2024 - Sept. 2024
        text: >+
          *   Configured and tested updates for IoT smart sump pump mobile app,
          ensuring seamless hardware integration


          *   Redesigned UI/UX to improve aesthetic appeal and reduce feature
          discovery time by 30% through A/B testing


          *   Led data-driven optimizations (ideation to deployment) via
          cross-cultural teamwork & proactive problem solving

        actions: []
        elementId: null
        colors: bg-neutralAlt-fg-dark
        styles:
          self:
            padding:
              - pt-8
              - pl-8
              - pb-8
              - pr-8
            borderRadius: x-large
            flexDirection: row
            justifyContent: center
            textAlign: left
        image:
          type: ImageBlock
          altText: Lightning bolt symbol on red background
          elementId: ''
          styles:
            self:
              borderRadius: x-large
      - type: FeaturedItem
        title: Mathematics Tutor
        subtitle: Jan 2022 - Jan 2023
        text: >+
          *   Helped students to develop their own problem solving tools in
          mathematics, physics, and computer science


          *   Employed dynamic teaching strategies to engage and support
          students aged 16 to 60 in active learning

        actions: []
        colors: bg-neutralAlt-fg-dark
        styles:
          self:
            padding:
              - pt-8
              - pl-8
              - pb-8
              - pr-8
            borderRadius: x-large
            flexDirection: row
            justifyContent: center
            textAlign: left
    actions: []
    badge:
      label: ''
      color: text-primary
      styles:
        self:
          textAlign: center
      type: Badge
    elementId: ''
    variant: three-col-grid
    colors: bg-neutral-fg-dark
    styles:
      self:
        padding:
          - pb-16
          - pt-16
          - pl-16
          - pr-16
        justifyContent: center
      subtitle:
        textAlign: center
  - title:
      text: RESEARCH
      color: text-primary
      styles:
        self:
          textAlign: center
      type: TitleBlock
    subtitle: ''
    items:
      - title: Machine Learning
        tagline: This is the tagline
        subtitle: This is the item subtitle
        text: |
          Follow the tutorial to build your first Netlify Create site.
        image:
          url: /images/abstract-feature1.svg
          altText: Placeholder Image
          styles:
            self:
              borderRadius: x-large
          type: ImageBlock
        colors: bg-light-fg-dark
        styles:
          self:
            padding:
              - pt-8
              - pl-8
              - pb-8
              - pr-8
            borderRadius: x-large
            flexDirection: col
        type: FeaturedItem
      - title: Data Analysis
        tagline: This is the tagline
        subtitle: This is the item subtitle
        text: |
          Follow the tutorial to build your first awesome Netlify Create site.
        image:
          url: /images/abstract-feature2.svg
          altText: Placeholder image
          styles:
            self:
              borderRadius: x-large
          type: ImageBlock
        colors: bg-light-fg-dark
        styles:
          self:
            padding:
              - pt-8
              - pl-8
              - pb-8
              - pr-8
            borderRadius: x-large
            flexDirection: col
        type: FeaturedItem
      - title: Population Modeling
        tagline: This is the tagline
        subtitle: This is the item subtitle
        text: >
          Learn from the tutorial and build your first awesome Netlify Create
          site.
        image:
          url: /images/abstract-feature1.svg
          altText: Placeholder image
          styles:
            self:
              borderRadius: x-large
          type: ImageBlock
        colors: bg-light-fg-dark
        styles:
          self:
            padding:
              - pt-8
              - pl-8
              - pb-8
              - pr-8
            borderRadius: x-large
            flexDirection: col
        type: FeaturedItem
    variant: three-col-grid
    colors: bg-neutral-fg-dark
    styles:
      self:
        padding:
          - pt-16
          - pl-8
          - pb-16
          - pr-8
        justifyContent: center
      subtitle:
        textAlign: center
    type: FeaturedItemsSection
  - title: Divider
    colors: bg-light-fg-dark
    styles:
      self:
        padding:
          - pt-7
          - pl-7
          - pb-7
          - pr-7
    type: DividerSection
  - posts:
      - content/pages/blog/case-study-1.md
      - content/pages/blog/case-study-2.md
      - content/pages/blog/case-study-3.md
    showThumbnail: true
    showDate: true
    showAuthor: true
    variant: three-col-grid
    colors: bg-light-fg-dark
    styles:
      self:
        padding:
          - pt-16
          - pl-16
          - pb-16
          - pr-16
        justifyContent: center
      subtitle:
        textAlign: center
        fontWeight: 700
    type: FeaturedPostsSection
    hoverEffect: move-up
    subtitle: ''
    title:
      type: TitleBlock
      text: PROJECTS
      color: text-dark
      styles:
        self:
          textAlign: center
    actions:
      - type: Button
        label: See More
        altText: See More Projects
        url: /blog
        showIcon: false
        icon: arrowRight
        iconPosition: right
        style: primary
        elementId: ''
  - title:
      text: UCLA
      color: text-dark
      type: TitleBlock
    subtitle: B.S. Statistics and Data Science & Applied Mathematics
    text: |
      December 2025
    actions: []
    media:
      altText: Fun feature preview
      type: ImageBlock
    badge:
      label: Education
      color: text-primary
      type: Badge
    colors: bg-light-fg-dark
    styles:
      self:
        alignItems: center
    type: GenericSection
  - type: FeaturedItemsSection
    title:
      type: TitleBlock
      text: AWARDS
      color: text-dark
      styles:
        self:
          textAlign: center
    subtitle: ''
    items:
      - type: FeaturedItem
        title: 1st Place STEM Poster
        subtitle: 2023 UCI CC Honors Research Conference
        text: >
          First place STEM Poster in regional research conference among hundreds
          of presentations!


          **Seven Billion Alaskan Snow Crabs Vanished. What happened?**


          A data visualization analysis exploring the reasons for a historic and
          drastic decline in Alaskan snow crab populations. We incorporated
          ocean temperature data, survey population data of snow crabs and
          Pacific cod (their primary predator), and time into our dynamic
          visualizations.
        actions: []
        colors: bg-neutral-fg-dark
        styles:
          self:
            padding:
              - pt-8
              - pl-8
              - pb-8
              - pr-8
            textAlign: left
            borderRadius: x-large
            flexDirection: row
            justifyContent: center
      - type: FeaturedItem
        title: 1st Place (tie) STEM Poster
        subtitle: 2022 UCI CC Research Conference
        text: >
          **Mathematical Modeling of California Condor and Grey Wolf Populations
          with Restoration Efforts**


          A comparison of population recovery programs of the California condor
          and Yellowstone gray wolf populations using a logistical population
          growth model and the Lotka-Volterra (predator-prey) model.
        actions: []
        colors: bg-neutral-fg-dark
        styles:
          self:
            padding:
              - pt-8
              - pl-8
              - pb-8
              - pr-8
            textAlign: left
            borderRadius: x-large
            flexDirection: row
            justifyContent: center
        tagline: ''
      - type: FeaturedItem
        title: 1st Place Persuasive Speech
        subtitle: 2022 PSCFA Cool-Off Tournament
        text: >
          Regional forensics tournament among speech teams across the state of
          California.
        actions: []
        colors: bg-neutral-fg-dark
        styles:
          self:
            padding:
              - pt-8
              - pl-8
              - pb-8
              - pr-8
            borderRadius: x-large
            flexDirection: row
      - type: FeaturedItem
        title: 1st Place Speech
        subtitle: 2022 Irvine Valley College Intramural Communications Tournament
        text: |
          Best speech out of over 60 competitors in honors IVC speech classes.
        actions: []
        colors: bg-neutral-fg-dark
        styles:
          self:
            padding:
              - pt-8
              - pl-8
              - pb-8
              - pr-8
            textAlign: left
            borderRadius: x-large
            flexDirection: row
            justifyContent: center
    actions: []
    variant: toggle-list
    colors: bg-light-fg-dark
    styles:
      self:
        padding:
          - pb-40
          - pt-16
          - pl-3
          - pr-3
        justifyContent: center
      subtitle:
        textAlign: center
  - title: Divider
    colors: bg-light-fg-dark
    styles:
      self:
        padding:
          - pt-7
          - pl-7
          - pb-7
          - pr-7
    type: DividerSection
  - title:
      text: CONTACT
      color: text-dark
      type: TitleBlock
    subtitle: ''
    text: >
      Please feel free to drop me a message about anything at all. I love
      hearing from anyone and everyone!
    media:
      fields:
        - name: name
          label: Name
          hideLabel: true
          placeholder: Your name
          isRequired: true
          width: full
          type: TextFormControl
        - name: email
          label: Email
          hideLabel: true
          placeholder: Your email
          isRequired: true
          width: full
          type: EmailFormControl
        - name: message
          label: Message
          hideLabel: true
          placeholder: Your message
          width: full
          type: TextareaFormControl
      elementId: contact-form
      styles:
        self:
          padding:
            - pt-6
            - pb-6
            - pl-6
            - pr-6
          borderColor: border-dark
          borderStyle: solid
          borderWidth: 1
          borderRadius: large
      type: FormBlock
      submitButton:
        type: SubmitButtonFormControl
        label: Submit
        showIcon: false
        icon: arrowRight
        iconPosition: right
        style: primary
        elementId: null
    badge:
      label: Say hi!
      color: text-primary
      type: Badge
    colors: bg-light-fg-dark
    type: GenericSection
seo:
  metaTitle: Home - Demo site
  metaDescription: This demo site is built with Netlify Create.
  socialImage: /images/main-hero.jpg
  type: Seo
type: PageLayout
---
