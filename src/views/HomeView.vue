<template>
  <div class="home">
    <div class="home__menu">
      <h2>Dashboard <span>v.1</span></h2>
      <div>
        <div class="option">
          <p>Income</p>
          <span>></span>
        </div>
        <div class="option dash">
          <p>Dashboard</p>
          <span>></span>
        </div>
        <div class="option">
          <p>Promote</p>
          <span>></span>
        </div>
        <div class="option">
          <p>Help</p>
          <span>></span>
        </div>
      </div>
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
          <div>
            <div v-for="(person, index) in personDataList" :key="index">
              <PersonComponent
                :name="person.name"
                :email="person.email"
                :phone="person.phone"
                :company="person.company"
                :country="person.country"
                :color="person.color"
                :status="person.status"
              />
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
import PersonComponent from '@/components/PersonComponent.vue'
import MenuOption from '@/components/MenuOption.vue'

@Component({
  components: {
    PersonComponent,
    MenuOption,
  },
})
export default class HomeView extends Vue {
  menuOptions = [
    {
      text: 'Dashboard',
    },
    {
      text: 'Income',
    },
    {
      text: 'Product',
    },
    {
      text: 'Promote',
    },
    {
      text: 'Help',
    },
  ]
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
      company: 'Global',
      country: 'UK',
      color: 'green',
      status: 'Pending',
    },
    {
      name: 'Michael Brown',
      email: 'michael@example.com',
      phone: '321654987',
      company: 'Innovate.',
      country: 'Australia',
      color: 'red',
      status: 'Completed',
    },
    {
      name: 'Emily Wilson',
      email: 'emily@example.com',
      phone: '789654123',
      company: 'Creative',
      country: 'Germany',
      color: 'green',
      status: 'Processing',
    },
    {
      name: 'Daniel Lee',
      email: 'daniel@example.com',
      phone: '159357468',
      company: 'Innovations',
      country: 'France',
      color: 'green',
      status: 'Blocked',
    },
  ]
}
console
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
    padding: 32px;

    .dash {
      background-color: #5932ea;
      color: white;
    }
    .option {
      border-radius: 12px;
      padding: 16px;
      display: flex;
      justify-content: space-between;
      span {
        font-size: 20px;
      }
    }

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
          text-align: center;
          span {
            flex: 1;
          }
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
