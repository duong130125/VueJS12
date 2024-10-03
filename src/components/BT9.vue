<template>
  <div>
    <h2>Bài 9:</h2>
    <v-container>
      <v-row>
        <!-- Basic Layout Column -->
        <v-col cols="12" md="6">
          <v-card>
            <v-card-title>Basic Layout</v-card-title>
            <v-card-text>
              <v-form>
                <label for="name">Name</label>
                <v-text-field
                  id="name"
                  placeholder="John Deo"
                  density="compact"
                  variant="outlined"
                ></v-text-field>

                <label for="company">Company</label>
                <v-text-field
                  id="company"
                  placeholder="ACME Inc."
                  density="compact"
                  variant="outlined"
                ></v-text-field>

                <label for="email">Email</label>
                <v-text-field
                  id="email"
                  placeholder="john.deo@example.com"
                  density="compact"
                  variant="outlined"
                ></v-text-field>

                <label for="phone">Phone No</label>
                <v-text-field
                  id="phone"
                  placeholder="412 2150 451"
                  density="compact"
                  variant="outlined"
                ></v-text-field>

                <label for="message">Message</label>
                <v-textarea
                  id="message"
                  placeholder="Hi, Do you have a moment to talk Jeo?"
                  density="compact"
                  variant="outlined"
                ></v-textarea>

                <v-btn color="primary" size="small" class="mt-3">Send</v-btn>
              </v-form>
            </v-card-text>
          </v-card>
        </v-col>

        <!-- Basic with Icons Column -->
        <v-col cols="12" md="6">
          <v-card>
            <v-card-title>Basic with Icons</v-card-title>
            <v-card-text>
              <v-form>
                <label for="name-icon">Name</label>
                <v-text-field
                  id="name-icon"
                  placeholder="John Deo"
                  density="compact"
                  variant="outlined"
                  prepend-inner-icon="mdi-account"
                ></v-text-field>

                <label for="company-icon">Company</label>
                <v-text-field
                  id="company-icon"
                  placeholder="ACME Inc."
                  density="compact"
                  variant="outlined"
                  prepend-inner-icon="mdi-briefcase"
                ></v-text-field>

                <label for="email-icon">Email</label>
                <v-text-field
                  id="email-icon"
                  placeholder="john.deo@example.com"
                  density="compact"
                  variant="outlined"
                  prepend-inner-icon="mdi-email"
                ></v-text-field>

                <label for="phone-icon">Phone No</label>
                <v-text-field
                  id="phone-icon"
                  placeholder="412 2150 451"
                  density="compact"
                  variant="outlined"
                  prepend-inner-icon="mdi-phone"
                ></v-text-field>

                <label for="message-icon">Message</label>
                <v-textarea
                  id="message-icon"
                  placeholder="Hi, Do you have a moment to talk Jeo?"
                  density="compact"
                  variant="outlined"
                  prepend-inner-icon="mdi-message"
                ></v-textarea>

                <v-btn color="primary" size="small" class="mt-3">Send</v-btn>
              </v-form>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script setup></script>

<style scoped>
.v-card {
  padding: 16px;
}
.v-text-field,
.v-textarea {
  margin-bottom: 16px;
}
.v-btn {
  width: auto;
  align-self: flex-end;
}
</style>
