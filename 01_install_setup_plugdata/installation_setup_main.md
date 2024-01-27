---
layout: default
title: Installation and setting up Plugdata with Daisy
nav_order: 1
has_children: true
---
# Documentation in this folder:

- [What is Plugdata](\01_what_is_plugdata.md)
  * A brief overview of programming a Daisy seed using the visual patching method.
- [Installing Plugdata and the toolchain](\02_installation_toolchain.md)
  - Download Plugdata
  - installing the toolchain and using the compiler window
- [Creating a custom json](01_install_setup_plugdata\03_custom_json_board\03_custom_json_board.md) 
  - Describing your board and which components are connected to which pins

{: .highlight }
> 💡 TO DO: Link README for Github, checking links

***

<button class="btn js-toggle-dark-mode">Toggle dark / light theme</button>

<script>
const toggleDarkMode = document.querySelector('.js-toggle-dark-mode');

jtd.addEvent(toggleDarkMode, 'click', function(){
  if (jtd.getTheme() === 'dark') {
    jtd.setTheme('light');
    toggleDarkMode.textContent = 'set dark theme';
  } else {
    jtd.setTheme('dark');
    toggleDarkMode.textContent = 'set light theme';
  }
});
</script>