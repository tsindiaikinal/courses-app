<template>
  <div>
    <v-row id="modal-win">
      <v-dialog v-model="dialog" persistent max-width="500px">
        <template v-slot:activator="{ on }">
          <v-btn color fab id="add-btn" v-on="on" style="width: 40px">
            <span class="btn-text">+</span>
          </v-btn>
        </template>
        <v-card>
          <v-card-title>
            <span class="headline">{{ profile }}</span>
          </v-card-title>
          <v-card-text>
            <v-container>
              <v-row>
                <v-col cols="12" sm="6" md="6">
                  <v-text-field
                    label="Name*"
                    hint="Enter your name"
                    required
                    v-model.lazy="defaultItem.name"
                  ></v-text-field>
                </v-col>
                <v-col cols="12" sm="6" md="6">
                  <v-text-field
                    label="Email*"
                    hint="Enter your email"
                    required
                    v-model.lazy="defaultItem.email"
                  ></v-text-field>
                </v-col>
                <v-col cols="12" sm="6">
                  <v-select :items="userStatus" label="Status" v-model="defaultItem.status"></v-select>
                </v-col>
              </v-row>
            </v-container>
            <small>*indicates required field</small>
          </v-card-text>

          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn color="blue darken-1" text @click="dialog = false">Close</v-btn>
            <v-btn color="blue darken-1" text @click="addUsers">Save</v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </v-row>
  </div>
</template>

<script>
export default {
  name: "DialogWindow",
  props: ["popupData"],
  data() {
    return {
      dialog: true,
      profile: "New contact",
      editedIndex: -1,
      userStatus: ["Active", "Inactive"],
      defaultItem: {
        name: "",
        email: "",
        status: ""
      },
      editedItem: {
        name: "",
        email: "",
        status: ""
      },
      users: [],
      // valid: true,
      nameRules: [
        v => !!v || "Name is required",
        v => (v && v.length <= 20) || "Name must be less than 20 characters"
      ],
      email: "",
      rules: {
        required: value => !!value || "Email is Required.",
        counter: value => value.length <= 20 || "Max 20 characters",
        email: value => {
          const pattern = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
          return pattern.test(value) || "Invalid e-mail.";
        }
      }
    };
  },
  computed: {
    formTitle() {
      return this.editedIndex === -1
        ? "Новый контакт"
        : "Редактировать контакт";
    }
  },
  methods: {
    addUsers() {
      this.editedItem = Object.assign({}, this.defaultItem);
      // if (this.editedIndex > -1) {}
      this.users.push(this.editedItem);
      this.dialog = false;
      dataTransfer();
    },
    dataTransfer() {
      this.$emit("formDataTransfer", this.editedItem);
    }
  },
  watch: {
    "defaultItem.email": () => {
      alert(this.defaultItem.email);
    }
  },
  components: {}
};
</script>

<style lang="scss" scoped>
// COLORS
$lgrey: lightgrey;
$lblack: #35495e;
$white: #ffffff;
$lgreen: #59b983;
$red: #f60000;
// **************

#modal-win {
  width: 60px;
}

#add-btn {
  width: 40px;
  height: 40px;
  font-size: 1.7rem;
  cursor: pointer;
  color: $white;
  background: $red;
}
.btn-text {
  display: inline-block;
  margin-top: -5px;
  text-shadow: 0 1px 2px #000;
}

.add-icon {
  width: 100%;
  line-height: 40px;
}
.fa-user {
  position: absolute;
  top: 30%;
  left: 25%;
  padding-right: 25px;
}
#dialog {
  max-width: 500px;
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  box-shadow: 0 0 5px 100vw rgba(0, 0, 0, 0.5);
}
// .bar-shadow {
//   box-shadow: 0 2px 3px 1px rgba(0, 0, 0, 0.2);
// }
// .non-shadow {
//   box-shadow: 0 0 4px 1px rgba(0, 0, 0, 0.2);
// }
// #addfiles {
//   /* background: red; */
//   border: 1px solid grey;
//   color: #28a745;
//   margin-top: 15px;
//   border-radius: 4px;
// }

// .custom-loader {
//   animation: loader 1s infinite;
//   display: flex;
// }
// @-moz-keyframes loader {
//   from {
//     transform: rotate(0);
//   }
//   to {
//     transform: rotate(360deg);
//   }
// }
// @-webkit-keyframes loader {
//   from {
//     transform: rotate(0);
//   }
//   to {
//     transform: rotate(360deg);
//   }
// }
// @-o-keyframes loader {
//   from {
//     transform: rotate(0);
//   }
//   to {
//     transform: rotate(360deg);
//   }
// }
// @keyframes loader {
//   from {
//     transform: rotate(0);
//   }
//   to {
//     transform: rotate(360deg);
//   }
// }
</style>
