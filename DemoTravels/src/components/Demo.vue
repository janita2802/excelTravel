<template>
  <div
    class="max-w-3xl mx-auto p-6 bg-gradient-to-r from-indigo-50 to-purple-50 shadow-lg rounded-xl border border-gray-300"
  >
    <div class="flex justify-between items-center mb-6">
      <div class="text-sm text-indigo-600">{{ email }}</div>
      <div class="text-3xl font-semibold text-purple-700">
        {{ companyName }}
      </div>
    </div>

    <div class="text-center mb-6">
      <h2 class="text-3xl font-extrabold text-indigo-900 mb-1">DUTY SLIP</h2>
      <vue-datepicker
        v-model="selectedDate"
        @update:model-value="updateDate"
        class="w-40 mx-auto"
      />
    </div>

    <div class="mb-4">
      <div class="flex items-center mb-2">
        <label class="w-24 font-medium text-gray-700">Party:</label>
        <input
          type="text"
          v-model="partyName"
          class="border border-gray-300 px-3 py-2 rounded-md focus:ring focus:ring-indigo-200"
        />
      </div>
      <div class="flex items-start mb-2">
        <label class="w-24 font-medium text-gray-700">Address:</label>
        <textarea
          v-model="address"
          class="border border-gray-300 px-3 py-2 rounded-md focus:ring focus:ring-indigo-200"
        ></textarea>
      </div>
      <div class="flex items-center mb-2">
        <label class="w-24 font-medium text-gray-700">Phone:</label>
        <input
          type="text"
          v-model="phone"
          class="border border-gray-300 px-3 py-2 rounded-md focus:ring focus:ring-indigo-200"
        />
      </div>
    </div>

    <div class="grid grid-cols-2 gap-4 mb-6">
      <div>
        <div class="flex items-center mb-2">
          <label class="w-24 font-medium text-gray-700">Bus No.:</label>
          <input
            type="text"
            v-model="busNo"
            class="border border-gray-300 px-3 py-2 rounded-md focus:ring focus:ring-indigo-200"
          />
        </div>
        <div class="flex items-center mb-2">
          <label class="w-24 font-medium text-gray-700">Date From:</label>
          <vue-datepicker v-model="dateFrom" class="w-40" />
        </div>
        <div class="flex items-center mb-2">
          <label class="w-24 font-medium text-gray-700">Closing Kms.:</label>
          <input
            type="text"
            v-model="closingKms"
            class="border border-gray-300 px-3 py-2 rounded-md focus:ring focus:ring-indigo-200"
          />
        </div>
      </div>

      <div>
        <div class="flex items-center mb-2">
          <label class="w-24 font-medium text-gray-700">Time:</label>
          <vue-datepicker v-model="time" type="time" class="w-40" />
        </div>
        <div class="flex items-center mb-2">
          <label class="w-24 font-medium text-gray-700">To:</label>
          <vue-datepicker v-model="dateTo" class="w-40" />
        </div>
        <div class="flex items-center mb-2">
          <label class="w-24 font-medium text-gray-700">Total Hours:</label>
          <input
            type="text"
            v-model="totalHours"
            class="border border-gray-300 px-3 py-2 rounded-md focus:ring focus:ring-indigo-200"
          />
        </div>
      </div>
    </div>

    <div class="mb-4">
      <p class="font-medium text-gray-700">
        Please Pay Balance Rs. ______ to Driver Before Start
      </p>
      <div class="grid grid-cols-2 gap-4 text-gray-700">
        <p>Extra Km. @ Rs. ______ Per Km.</p>
        <p>Extra Hrs. @ Rs. ______ Per Hr.</p>
        <p>Tax Rs.: ______</p>
        <p>D.A. Rs.: ______ Per day</p>
      </div>
      <div class="flex items-center mt-3">
        <label class="w-24 font-medium">Mumbai to:</label>
        <input
          type="text"
          v-model="tripRoute"
          class="border border-gray-400 px-3 py-2 rounded-md focus:ring focus:ring-indigo-200"
        />
      </div>
    </div>

    <div class="text-sm text-gray-700">
      <p>KILOMETERS AND TIMING WILL BE CHARGED FROM GARAGE TO GARAGE.</p>
      <p>TOLL TAX, ENTRY, PARKING TO BE PAID BY PARTY.</p>
    </div>

    <div class="text-right mt-4">
      <div class="border-t pt-2 font-medium">Client's Signature</div>
    </div>
  </div>
</template>

<script>
import VueDatepicker from "@vuepic/vue-datepicker";
import "@vuepic/vue-datepicker/dist/main.css";

export default {
  name: "Receipt",
  components: {
    VueDatepicker,
  },
  data() {
    return {
      email: "excel.travel@rediffmail.com",
      companyName: "Excel Travels",
      selectedDate: new Date(),
      dateFrom: new Date(),
      dateTo: new Date(),
      time: new Date(),
      partyName: "",
      address: "",
      phone: "",
      busNo: "",
      closingKms: "",
      totalHours: "",
      tripRoute: "",
    };
  },
  methods: {
    updateDate(value) {
      this.selectedDate = value;
    },
  },
};
</script>

<style scoped>
input:focus,
textarea:focus {
  outline: none;
  border-color: #6366f1;
  box-shadow: 0 0 5px #6366f1;
}
</style>
