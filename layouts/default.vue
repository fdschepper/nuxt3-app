<template>
    <div style="top: 0;">
        <nav id="navbar">
            <ul>
                <li>
                    <NuxtLink to="/">home</NuxtLink>
                </li>
                <li>
                    <NuxtLink to="/about">about</NuxtLink>
                </li>
                <li>
                    <NuxtLink to="/post">post</NuxtLink>
                </li>
            </ul>
        </nav>
        <slot />
    </div>
</template>

<style>
@font-face {
    font-family: "puff";
    src: url('puffe.ttf')
}

#navbar {
    width: 100%;
    margin-top: 0px;
}

#navbar ul {
    display: flex;
    justify-content: space-evenly;
    background-color: #c3eff3;
    padding: 0%;
}

#navbar ul li {

    display: inherit;

}

#navbar ul li a {
    font-family: puff;
    padding: 20%;
    background-color: #edfcf2;
    border-radius: 8px;
    text-decoration: none;
    color: black;
    font-size: 30px;
    font-weight: 100;
    padding-left: 80%;
    padding-right: 80%;
    border: 4px solid #1ab575;
}

#navbar ul li a:hover {
    background-color: #cadcd0;
}
</style>

