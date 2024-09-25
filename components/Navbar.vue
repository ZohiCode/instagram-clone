<template>
  <nav class="fixed top-0 left-0 w-full z-50">
    <div class="container mx-auto">
      <h1>Instagram</h1>
      <ul class="flex space-x-4">
        <li>

          <NuxtLink to="/explore"><svg class="me-1" width="31px" height="31px" viewBox="0 0 24 24"
              xmlns="http://www.w3.org/2000/svg">
              <path
                d="M6.45 17.216l7.981-3.845 2.98-7.115-7.116 2.98zm6.741-4.358l-4.599 2.216 2.216-4.6zM12 1.2A10.8 10.8 0 1 0 22.8 12 10.812 10.812 0 0 0 12 1.2zm0 20.6a9.8 9.8 0 1 1 9.8-9.8 9.81 9.81 0 0 1-9.8 9.8z" />
              <path fill="none" d="M0 0h24v24H0z" />
            </svg></NuxtLink>
        </li>
        <li>

          <NuxtLink to="/">
            <svg class="me-1" width="30px" height="30px" viewBox="0 0 24 24" fill="none"
              xmlns="http://www.w3.org/2000/svg">
              <path d="M12 13V19" stroke="#000000" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" />
              <path
                d="M3 10.49C3 7.36999 8.87 2 12 2C15.13 2 21 7.36999 21 10.49V18.07C20.9816 19.1187 20.5521 20.1182 19.804 20.8533C19.0558 21.5883 18.0488 22.0002 17 22H7C5.95115 22.0002 4.9442 21.5883 4.19603 20.8533C3.44786 20.1182 3.01835 19.1187 3 18.07V10.47"
                stroke="#000000" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" />
            </svg>
          </NuxtLink>
        </li>
        <li>

          <NuxtLink to="/notification"><svg class="me-1" width="29px" height="29px" viewBox="0 0 24 24" fill="none"
              xmlns="http://www.w3.org/2000/svg">
              <path
                d="M12 3H6C4.93913 3 3.92172 3.42149 3.17157 4.17163C2.42142 4.92178 2 5.93913 2 7V14C2 15.0609 2.42142 16.0783 3.17157 16.8285C3.92172 17.5786 4.93913 18 6 18H8L10.29 20.29C10.514 20.5156 10.7804 20.6946 11.0739 20.8168C11.3674 20.9389 11.6821 21.0018 12 21.0018C12.3179 21.0018 12.6326 20.9389 12.9261 20.8168C13.2196 20.6946 13.486 20.5156 13.71 20.29L16 18H18C19.0609 18 20.0783 17.5786 20.8284 16.8285C21.5786 16.0783 22 15.0609 22 14V10"
                stroke="#000000" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" />
              <path
                d="M20.6 1.00003C20.008 1.00175 19.4377 1.2171 19 1.60422C18.6567 1.30103 18.23 1.10139 17.7719 1.02963C17.3138 0.957876 16.844 1.0171 16.42 1.20011C15.9959 1.38311 15.6359 1.68198 15.3838 2.06026C15.1316 2.43854 14.9983 2.87989 15 3.33048C15 6.11406 19 8 19 8C19 8 23 6.11406 23 3.33048C23 2.71241 22.7472 2.11966 22.2971 1.68261C21.847 1.24557 21.2365 1.00003 20.6 1.00003Z"
                stroke="#000000" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" />
            </svg> </NuxtLink>
        </li>
        <li>

          <NuxtLink to="/profile"><svg class="me-1" width="30px" height="30px" viewBox="0 0 24 24" fill="none"
              xmlns="http://www.w3.org/2000/svg">
              <path
                d="M12.1992 12C14.9606 12 17.1992 9.76142 17.1992 7C17.1992 4.23858 14.9606 2 12.1992 2C9.43779 2 7.19922 4.23858 7.19922 7C7.19922 9.76142 9.43779 12 12.1992 12Z"
                stroke="#000000" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" />
              <path
                d="M3 22C3.57038 20.0332 4.74796 18.2971 6.3644 17.0399C7.98083 15.7827 9.95335 15.0687 12 15C16.12 15 19.63 17.91 21 22"
                stroke="#000000" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" />
            </svg></NuxtLink>
        </li>

      </ul>
    </div>
  </nav>
</template>

<script lang="ts">
export default {};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Billabong&display=swap");
@import url("https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css");

nav {
  border-bottom: 1px solid #dfdede;
  width: 100%;
  background-color: #fff;

}

div {
  background-color: #fff;
  padding: 10px;
}

div h1 {
  display: inline;
  font-family: "Billabong", cursive;
  font-size: 1.5rem;
  color: #000;
  margin: 0;
  cursor: pointer;
}

div ul {
  list-style: none;
  float: right;
}
</style>
