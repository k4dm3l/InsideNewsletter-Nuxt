<template>
  <!-- Editable table -->
  <div class="card">
    <h3 class="card-header text-center font-weight-bold text-uppercase py-4">
      Newsletters
    </h3>
    <div class="card-body">
      <div v-if="newsletters.length > 0" id="table" class="table-editable">
        <span class="table-add float-right mb-3 mr-2">
          <a
            class="text-success"
            data-toggle="modal"
            data-target="#register-newsletter"
          >
            <i class="fas fa-plus fa-2x" aria-hidden="true"></i>
          </a>
        </span>
        <table
          class="table table-bordered table-responsive-md table-striped text-center"
        >
          <thead>
            <tr>
              <th class="text-center">Id</th>
              <th class="text-center">Title</th>
              <th class="text-center">Target</th>
              <th class="text-center">Subscribed</th>
              <th class="text-center">Action</th>
            </tr>
          </thead>
          <tbody align="center">
            <tr
              v-for="newsletter in newsletters"
              :key="newsletter.id"
              :id="newsletter.id"
            >
              <td class="pt-3-half" contenteditable="false">
                {{ newsletter.id }}
              </td>
              <td class="pt-3-half" contenteditable="false">
                {{ newsletter.title }}
              </td>
              <td class="pt-3-half" contenteditable="false">
                {{ newsletter.target }}
              </td>
              <td class="pt-3-half" contenteditable="false">
                {{ newsletter.subscribed }}
              </td>
              <td>
                <span class="table-remove">
                  <button
                    @click="deleteNewsletter(newsletter.id)"
                    type="button"
                    class="btn btn-danger btn-rounded btn-sm my-0"
                  >
                    <i class="fas fa-trash"></i>
                  </button>
                </span>
                <span class="table-remove">
                  <a
                    :newsletter_data="newsletter"
                    @click="updateNewsletter(newsletter.id)"
                    class="btn btn-info btn-rounded btn-sm my-0"
                    data-toggle="modal"
                    data-target="#update-newsletter"
                  >
                    <i class="fas fa-pen-alt"></i>
                  </a>
                </span>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
      <h3 class="text-center" v-else>Upss.. No records here! :D</h3>
    </div>
  </div>
  <!-- Editable table -->
</template>
<script>
import axios from 'axios'
import Swal from 'sweetalert2'
export default {
  name: 'dashboard-principal',
  data() {
    return {
      url_end_point: `${process.env.apiURL}/newsletters`,
      newsletters: []
    }
  },
  created() {
    this.getAllNewsletters()
  },
  methods: {
    getAllNewsletters() {
      const endpoint = this.url_end_point

      axios
        .get(endpoint)
        .then((response) => {
          this.newsletters = response.data
        })
        .catch((err) => {
          alert(err)
        })
    },
    updateNewsletter(idElement) {
      const updObject = this.newsletters.find((newsletter) => {
        return newsletter.id === idElement
      })
      alert(updObject.id)
    },
    deleteNewsletter(idElement) {
      const endpoint = this.url_end_point
      const aux = this.newsletters
      this.newsletters = []

      axios
        .delete(`${endpoint}/${idElement}`)
        .then((response) => {
          if (response.status === 204) {
            Swal.fire({
              type: 'success',
              title: 'Deleted',
              text: `Row deleted!`
            })

            aux.forEach((newsletter) => {
              if (newsletter.id !== idElement) {
                this.newsletters.push(newsletter)
              }
            })
          } else {
            Swal.fire({
              type: 'Ooops...',
              title: 'Something happen here',
              text: `The server response with something... rare!`
            })
          }
        })
        .catch((err) => {
          Swal.fire({
            type: 'Ooops...',
            title: 'Request Failed',
            text: `${err}`
          })
        })
    }
  }
}
</script>
<style scoped></style>
