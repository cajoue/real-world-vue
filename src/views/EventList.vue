<template>
  <h1>Events for good</h1>
  <div class="events">
    <EventCard v-for="event in events" :key="event.id" :event="event" />
  </div>
</template>

<script>
// @ is an alias to /src
import EventCard from "@/components/EventCard.vue"
import EventService from "@/services/EventService.js";

export default {
  name: "EventList",
  components: {
    EventCard,
  },
  data() {
    return {
      events: null,
    }
  },
  created() {
    // lifecycle hook to get events from mock db when component is created
    EventService.getEvents()
      .then((response) => {
        this.events = response.data
      })
      .catch((error) => {
        console.log(error)
      })
  },
}

/* a parent component (EventList) creates child components (EventCard)
it holds data (events) to feed to child components having a 'prop' (:event) 

As we iterate over the events array to create a new EventCard for each event object, 
we pass that event object into a new :event prop that we added to the EventCard. 
Each EventCard then has all of the data it needs to display its own event info.

Life cycle hooks : 
a component has a lifecycle and different hooks (methods) are run at different stages in its lifecycle. 
eg: before created, when created, before mounted, after mounted ...
*/
</script>

<style scoped>
.events {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
