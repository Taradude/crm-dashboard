<template>
  <div class="home">
    <div class="home__menu">
      <h2>Dashboard <span>v.1</span></h2>
    </div>
    <div class="home__dashboard">
      <h1>Hello , Evano 👋</h1>
      <div class="home__dashboard__list">
        <div class="top">
          <div>
            <h2>All customers</h2>
            <span>Active members</span>
          </div>
          <div class="input-wrap">
            <input type="text" placeholder="search" />
            <img src="@/assets/search.png" alt="" />
          </div>
        </div>
        <div class="bottom">
          <div class="header">
            <span>Customer name</span>
            <span>Company</span>
            <span>Phone number</span>
            <span>Email</span>
            <span>Country</span>
            <span>Status</span>
          </div>
          <hr />
          <PersonComponent
            v-for="(personData, index) in personDataList"
            :key="index"
            :name="personData.name"
            :email="personData.email"
            :phone="personData.phone"
            :company="personData.company"
            :country="personData.country"
            :color="personData.color"
            :status="personData.status"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import PersonComponent from '@/components/PersonComponent.vue'
import StatusComponent from '@/components/StatusComponent.vue'

@Component({
  components: {
    PersonComponent,
    StatusComponent,
  },
})
export default class HomeView extends Vue {
  personDataList = [
    {
      name: 'John Doe',
      email: 'john@example.com',
      phone: '123456789',
      company: 'ACME Inc.',
      country: 'USA',
      color: 'green',
      status: 'Active',
    },
    {
      name: 'Jane Smith',
      email: 'jane@example.com',
      phone: '987654321',
      company: 'Tech Corp',
      country: 'Canada',
      color: 'red',
      status: 'Inactive',
    },
    {
      name: 'Alice Johnson',
      email: 'alice@example.com',
      phone: '456123789',
      company: 'Global Enterprises',
      country: 'UK',
      color: 'green',
      status: 'Pending',
    },
    {
      name: 'Michael Brown',
      email: 'michael@example.com',
      phone: '321654987',
      company: 'Innovate Co.',
      country: 'Australia',
      color: 'green',
      status: 'Completed',
    },
    {
      name: 'Emily Wilson',
      email: 'emily@example.com',
      phone: '789654123',
      company: 'Creative Solutions',
      country: 'Germany',
      color: 'green',
      status: 'Processing',
    },
    {
      name: 'Daniel Lee',
      email: 'daniel@example.com',
      phone: '159357468',
      company: 'Tech Innovations',
      country: 'France',
      color: 'green',
      status: 'Blocked',
    },
  ]
}
</script>

<style scoped lang="scss">
.home {
  display: flex;
  flex-direction: row;
  height: 100%;

  &__menu {
    width: 25%;
    height: 100%;
    text-align: left;
    padding: 24px;
    span {
      font-size: 10px;
      color: grey;
    }
  }

  &__dashboard {
    height: 100%;
    background-color: gainsboro;
    width: 75%;
    padding: 64px;
    text-align: left;

    &__list {
      width: 100%;
      height: 100%;
      padding: 16px;
      background-color: white;
      border-radius: 20px;

      .top {
        padding: 12px;
        display: flex;
        justify-content: space-between;

        span {
          color: green;
        }
        .input-wrap {
          position: relative;

          input {
            border-radius: 12px;
            border: none;
            background-color: rgba(220, 220, 220, 0.463);
            text-align: center;
            height: 100%;
            width: 100%;
          }
        }
        img {
          position: absolute;
          top: 50%;
          transform: translateY(-50%);
          left: 5px;
          max-width: 80%;
          max-height: 80%;
        }
      }
      .bottom {
        .header {
          padding: 6px;
          display: flex;
          flex-direction: row;
          justify-content: space-around;
        }
        span {
          color: grey;
          font-weight: bold;
        }
      }
    }
  }
}
</style>
