---
type: PageLayout
title: Careers
sections:
  - type: GenericSection
    title:
      type: TitleBlock
      text: About Me
      color: text-dark
      styles:
        self:
          textAlign: center
    subtitle: Some Non-trivial Personal Information
    text: >
      Fun fact: I have taught pole dancing in a foreign country and narrowly
      escaped being sex trafficked in a different one. Below are some hobbies of
      mine that may or may not be interesting to you!
    actions: []
    colors: bg-neutral-fg-dark
    backgroundImage:
      type: BackgroundImage
      url: /images/abstract-background.svg
      altText: altText of the image
      backgroundSize: cover
      backgroundPosition: center
      backgroundRepeat: no-repeat
      opacity: 100
    styles:
      self:
        padding:
          - pt-40
          - pl-4
          - pb-40
          - pr-4
        alignItems: center
        flexDirection: row-reverse
        justifyContent: center
      text:
        textAlign: center
      subtitle:
        textAlign: center
  - type: FeaturedPeopleSection
    title:
      type: TitleBlock
      text: Hobbies
      color: text-dark
      styles:
        self:
          textAlign: center
    people:
      - content/data/person1.json
      - content/data/person2.json
      - content/data/person3.json
      - content/data/person4.json
      - content/data/person5.json
      - content/data/person6.json
    actions: []
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
slug: /about
seo:
  type: Seo
  metaTitle: Careers - Demo site
  metaDescription: This is the careers page built with Netlify Create.
  socialImage: /images/main-hero.jpg
  metaTags: []
---
