<template>
    <div class="navbar navbar-expand-md container-fluid">
        <h3 class="nav-brand">SH Dictionary</h3>
        <ul class="navbar-nav">
            <li class="nav-item">
                <router-link to="/" class="nav-link">Home</router-link>
            </li>
            <li class="nav-item">
                <router-link to="/dictionary" class="nav-link">Dictionary</router-link>
            </li>
        </ul>
    </div>
</template>

<script>
export default{
    name:"Navbar"
}
</script>

<style scoped>
.navbar{
    background-color: #1d3557;
}
.nav-link{
    color:white;
}
.nav-link:hover{
    color:lavenderblush;
}
h3{
    color: white;
}
</style>
