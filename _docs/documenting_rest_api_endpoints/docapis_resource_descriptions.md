---
title: "Step 1: Resource description (API reference tutorial)"
permalink: /docapis_resource_descriptions.html
course: "Documenting REST APIs"
weight: 3.1
sidebar: docapis
section: docendpoints
path1: /docendpoints.html
---

{% include workflow_map.html step="1" map="content/reference_doc_map.html"  %}
{% if site.format == "pdf" or site.format == "kindle" %}
<img src="images/apiref1.png"/>
{% endif %}

> **{{site.data.apirefsections.resource_description.term}}**: {{site.data.apirefsections.resource_description.def}}

* TOC
{:toc}

## Example of a resource description {#examples}

Here's an example of a resource description from the Mailchimp API's [Campaigns resource](http://developer.mailchimp.com/documentation/mailchimp/reference/campaigns/#):

<a class="noExtIcon" href="http://developer.mailchimp.com/documentation/mailchimp/reference/campaigns/"><img src="images/mailchimpcampaigns.png"/></a>

Typically, an API will have a number of endpoints grouped under the same resource. Normally, you describe both the general resource and the individual endpoints. For example, the Campaigns resource has various endpoints that are also described:

* POST `/campaigns`
* GET `/campaigns	`
* GET `/campaigns/{campaign_id}`
* PATCH `/campaigns/{campaign_id}`
* DELETE `/campaigns/{campaign_id}`
* POST `/campaigns/{campaign_id}/actions/cancel-send`
* POST `/campaigns/{campaign_id}/actions/pause`
* POST `/campaigns/{campaign_id}/actions/replicate`
* POST `/campaigns/{campaign_id}/actions/resume`
* POST `/campaigns/{campaign_id}/actions/schedule`
* POST `/campaigns/{campaign_id}/actions/send`
* POST `/campaigns/{campaign_id}/actions/test`
* POST `/campaigns/{campaign_id}/actions/unschedule`

Here's a resource description for the Membership resource in the [Box API](https://docs.box.com/reference#membership-object):

<a  class="noCrossRef" href="https://docs.box.com/reference#membership-object" class="noExtIcon"><img src="images/boxapi_3_17.png" alt="Example from Box" /></a>

For the Membership resource (or "object," as they call it), there are 7 different endpoints or methods you can call. The Box API describes the Membership resource and each of the endpoints that let you access the resource.

Sometimes the general resource isn't described; instead, it just groups the endpoints. The bulk of the description appears in each endpoint. For example, in the Eventbrite API, here's the Events resource:

<a class="noExtIcon" href="https://www.eventbrite.com/developer/v3/endpoints/events/"><img src="images/eventbriteresourceexample.png"/></a>

Although the Events resource isn't described here, descriptions are added for each of the Events endpoints. The Events resource contains all of these endpoints:

* `/events/search/`
* `/events/`
* `/events/:id/`
* `/events/:id/`
* `/events/:id/publish/`
* `/events/:id/cancel/`
* `/events/:id/`
* `/events/:id/display_settings/`
* `/events/:id/display_settings/`
* `/events/:id/ticket_classes/`
* `/events/:id/ticket_classes/:ticket_class_id/`
* `/events/:id/canned_questions/`
* `/events/:id/questions/`
* `/events/:id/attendees/`
* `/events/:id/discounts`

And so on.

{: .tip}
When developers create APIs, they have a design question to consider: Use a lot of variants of endpoints (as with Eventbrite's API), or provide lots of parameters to configure the same endpoint. Often there's a balance between the two. The trend seems to be toward providing separate endpoints rather than supplying a host of potentially confusing parameters with the same endpoint.

As another example, here's the Relationships resource in the  [Instagram API](https://instagram.com/developer/endpoints/relationships/).

<a  class="noCrossRef" href="https://instagram.com/developer/endpoints/relationships/" class="noExtIcon"><img src="images/instagramapi_3_17.png"/></a>

The Relationships resource isn't described but rather acts as a container for relationship endpoints. Descriptions are added for each of the resources grouped within the Relationships resource:

* GET `/users/self/followsGet`
* GET `/users/self/followed-byGet`
* GET `/users/self/requested-byList`
* GET `/users/user-id/relationshipGet`
* POST `/users/user-id/relationshipModify`

{% include random_ad.html %}

For another example of an API with resources and endpoints, check out the [Trello API](https://developers.trello.com/v1.0/reference#introduction).

{: .tip}
The description of the resource is likely something you'll re-use in different places: product overviews, tutorials, code samples, quick references, etc. As a result, put a lot of effort into crafting it. Consider storing the description in a re-usable snippet in your authoring tool so that you can list it without resorting to copy/paste methods in your [quick start guide](docapis_doc_quick_reference.html).

## Terminology for describing the resource

The exact terminology for referring to resources varies. The "things" that you access using a URL can be referred to in a variety of ways, but "resource" is the most common term because you access them through a URL, or uniform *resource* locator. Other than "resources," you might see terms such as API calls, endpoints, API methods, calls, objects, services, and requests. Some docs get around the situation by not calling them anything explicitly.

Despite the variety with terminology, in general an API has various "resources" that you access through "endpoints." The endpoints give you access to the resource. (But terminology isn't standard, so expect variety.) The [Mashape Weather API](https://market.mashape.com/fyhao/weather-13) is pretty simple, and just refers to 3 "endpoints" available.

## Recognize the difference between reference docs versus user guides

Resource descriptions (as well as endpoint descriptions) are typically short, usually 1-3 sentences. What if you have a lot more detail to add? In these situations, keep in mind the difference between reference documentation and user guides/tutorials:

* **Reference documentation**: Concise, bare-bones information that developers can quickly reference.
* **User guides/tutorials**: More elaborate detail about how to use the API, including step-by-step instructions, code samples, concepts, and procedures.

Although the description in an API reference topic provides a 1-3 sentence summary of the information the resource contains, you might expand on this with much greater detail in the user guide. (You could link the reference description to the places in the guide where you provide more detail.)

## Resource description for the surfreport endpoint

{% include activity.html %}

Let's review the [surf report wiki page](docapis_new_endpoint_to_doc.html) (which contains the information about the resource) and try to describe the resource in 1-3 sentences. Here's my approach:

<div class="docSample">
{% include_relative surfreport_resource_description.html %}
</div>


## Next steps

Now it's time to list out the [Endpoints and methods](docapis_resource_endpoints.html) for the resource.
