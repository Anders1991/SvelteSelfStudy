<script>

const pages = ["Introduction","Reactivity","Props","Logic","Events"];

function closeAllPages() {
    var elems = document.getElementsByClassName('Page');
for (var i=0;i<elems.length;i+=1){
  elems[i].style.display = 'none';
}
};

function openPage() {
    closeAllPages();
	document.getElementById(pages[0]).style.display = "flex";
}

function openPage1() {
    closeAllPages();
    document.getElementById(pages[1]).style.display = "flex";
}

function openPage2() {
    closeAllPages();
    document.getElementById(pages[2]).style.display = "flex";
}

function openPage3() {
    closeAllPages();
    document.getElementById(pages[3]).style.display = "flex";
}

function openPage4() {
    closeAllPages();
    document.getElementById(pages[4]).style.display = "flex";
}
</script>

<div id="nav">
<button on:click={openPage}>Introduction</button>
<button on:click={openPage1}>Reactivity</button>
<button on:click={openPage2}>Props</button>
<button on:click={openPage3}>Logic</button>
<button on:click={openPage4}>Events</button>
</div>

<style>

#nav {
    display: flex;
    justify-content: center;
}

#nav button {
    margin: 2px;
}

</style>