<template>
  <div class="home">
    <Node :node="company.Uber" :handler="updateCurrent" :selected="current" />
    <div class="row">
      <Node
        v-for="value in company.Uber.children"
        :key="value.name"
        :node="value"
        :handler="updateCurrent"
        :selected="current"
      />
    </div>
    <div class="row" v-if="current in company.Uber.children">
      <Node
        v-for="value in company.Uber.children[current].children"
        :key="value.name"
        :node="value"
        :handler="updateCurrent"
        :selected="current"
      />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Node from "@/components/Node.vue";

export default {
  name: "Home",
  components: {
    Node
  },
  data: function() {
    return {
      current: "Uber",
      company: {
        Uber: {
          name: "Uber",
          position: "CEO",
          leader: "Dara Khosrowshahi",
          children: {
            Product: {
              name: "Product",
              position: "CPO",
              leader: "Dara Khosrowshahi",
              children: {
                "Product & Data Science": {
                  name: "Product & Data Science",
                  position: "VP of Technology",
                  leader: "Sundeep Jain"
                },
                "Payment (Uber Money)": {
                  name: "Payment (Uber Money)",
                  position: "Head",
                  leader: "Peter Hazlehurst"
                },
                "Product Design": {
                  name: "Product Design",
                  position: "VP",
                  leader: "Michael Gough"
                },
                "Global Scaled Solutions": {
                  name: "Global Scaled Solutions",
                  position: "Director",
                  leader: "Megha Yethadka"
                },
                "Business and Developer Products": {
                  name: "Business and Developer Products",
                  position: "Sr Director",
                  leader: "Eckart Walther"
                }
              }
            },
            Technology: {
              name: "Technology",
              position: "CTO",
              leader: "Thuan Pham",
              children: {
                "Product Engineering": {
                  name: "Product Engineering",
                  position: "VP of Technology",
                  leader: "Peeyush Nahar"
                },
                "Mobility & Marketplace": {
                  name: "Mobility & Marketplace",
                  position: "Head",
                  leader: "Gaurav Gang"
                },
                "Product Platform (business infrastructure)": {
                  name: "Product Platform (business infrastructure)",
                  position: "Sr Director",
                  leader: "Jennifer Anderson"
                },
                Infrastructure: {
                  name: "Infrastructure",
                  position: "Sr Director",
                  leader: "Sumanth Sukumar"
                },
                "Eats Engineering": {
                  name: "Eats Engineering",
                  position: "Sr Director",
                  leader: "Haider Sabri"
                },
                "Technical Program Management & Learning": {
                  name: "Technical Program Management & Learning",
                  position: "Sr Director",
                  leader: "Sophia Vicent"
                },
                "Information Technology": {
                  name: "Information Technology",
                  position: "CIO",
                  leader: "Shobhana Ahluwalla"
                }
              }
            },
            "Uber ATG": {
              name: "Uber ATG",
              position: "Head",
              leader: "Raquel Urtasun",
              children: {
                "Software Engineering": {
                  name: "Software Engineering",
                  position: "VP",
                  leader: "Jon Thomason"
                },
                "Systems Engineering & Testing": {
                  name: "Systems Engineering & Testing",
                  position: "Head",
                  leader: "Adrian Thompson"
                },
                "Hardware & Vehicle": {
                  name: "Hardware & Vehicle",
                  position: "Head",
                  leader: "Stephen Lesh"
                },
                "Supply Chain": {
                  name: "Supply Chain",
                  position: "Head",
                  leader: "Sameer Kshirsagar"
                },
                Safety: {
                  name: "Safety",
                  position: "Head",
                  leader: "Nat Beuse"
                },
                "Research & Development": {
                  name: "Research & Development",
                  position: "Head",
                  leader: "Raquel Urtasun"
                },
                "Product & Design": {
                  name: "Product & Design",
                  position: "Head",
                  leader: "Eric Hanson"
                },
                Strategy: {
                  name: "Strategy",
                  position: "Head",
                  leader: "Austin Geidt"
                }
              }
            },
            "Platform Growth & Customer Engagement": {
              name: "Platform Growth & Customer Engagement",
              position: "VP",
              leader: "Zhenya Lindgardt",
              children: {
                "Uber Works": {
                  name: "Uber Works",
                  position: "CEO",
                  leader: "Andrey Liscovich"
                },
                "Uber Transit": {
                  name: "Uber Transit",
                  position: "GM",
                  leader: "David Reich"
                },
                "Customer Engagement": {
                  name: "Customer Engagement",
                  position: "Head",
                  leader: "Jon Venuto"
                },
                Incubator: {
                  name: "Incubator",
                  position: "Head",
                  leader: "Karishma Shah"
                }
              }
            }
          }
        }
      }
    };
  },
  methods: {
    updateCurrent: function(newCurrent) {
      this.current = newCurrent;
    }
  }
};
</script>

<style scoped>
.row {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  margin: 0.1rem;
}
</style>
