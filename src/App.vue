<template>
  <div id="app" >
    <div id="note-main" class="note note--show" v-if="showNote">
      <div class="note__content">
        <div class="note__txt">
          <p><strong>GO TO HELL •</strong> Call <strong>or</strong> Txt <strong>(666) 666 6666</strong> <strong>•</strong> email <a href="mailto:fuckoff@ass.ru"><strong>fuckoff@ass.ru</strong></a></p>
          <span v-on:click="closeNote" class="note__close"></span>
        </div>
      </div>
    </div>
    <div class="layout">
      <navigation></navigation>
      <main class="main">
        <router-view></router-view>
      </main>
    </div>
  </div>
</template>

<script>
import Navigation from './components/navigation/Navigation'
export default {
  components: {
    'navigation': Navigation
  },
  name: 'app',
  data () {
    return {
      showNote: false
    }
  },
  methods: {
    closeNote: function () {
      this.showNote = false
    }
  }
}
</script>

<style lang="scss">
* {
	box-sizing: border-box;
}

html {
	font-size: 10px;
}

html, body {
	margin: 0;
	padding: 0;
}

body {
	font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
	font-size: 15px;
	line-height: 1.65;
}

ul, ol {
	margin: 0;
	padding: 0;
}

a {
	border-bottom: 1px solid rgba(20, 55, 90, .3); 
	color: rgb(20, 55, 90);
	cursor: pointer;
	outline: none;
	text-decoration: none;
}

a:hover {
	border-color: rgba(237, 22, 69, .3); 
	color: rgb(237, 22, 69);
}

.clr:before, .clr:after {
	content: '';
	clear: both;
	display: block;
	width: 100%;
}

.note {
	position: relative;
	background: #000000;
	display: none;
	opacity: 0;
	overflow: hidden;
	text-align: center;
	z-index: 1;
	-webkit-transition: opacity .3s;
	-moz-transition: opacity .3s;
	-o-transition: opacity .3s;
	transition: opacity .3s;
	/* -webkit-transition: height .3s cubic-bezier(.23,1,.32,1);
	-moz-transition: height .3s cubic-bezier(.23,1,.32,1);
	-o-transition: height .3s cubic-bezier(.23,1,.32,1);
	transition: height .3s cubic-bezier(.23,1,.32,1); */
	&--show {
		display: block;
		opacity: 1;
		z-index: 10000;
	}
	&__txt {
		color: #ffffff;
		padding: .8em 3em;
		font-family: Arial, Helvetica, sans-serif;
		font-size: .87em;
		text-transform: uppercase;
		letter-spacing: 2px;
		font-weight: 400;
		line-height: 1.2em;
		& p {
			margin: 0;
		}
	}
	&__close {
		cursor: pointer;
		position: absolute;
		top: 0;
		right: 0;
		width: 2.8em;
		height: 2.8em;
		background: rgba(0,0,0,.15);
		color: #fff;
		&::before {
			content: '×';
			display: block;
			font-family: Helvetica,Arial,sans-serif;
			font-size: 1em;
			font-weight: 100;
			line-height: 2.8em;
			letter-spacing: normal;
			padding: 0;
		}
	}
}

.layout {
	padding: 30px;
}

.form {
	position: relative;
	width: 100%;
	&_add {
		max-width: 450px;
	}
	&-wrapper {
    position: relative;
    margin: 5rem auto;
    padding: 3rem;
    width: 100%;
    min-width: 300px;
    max-width: 400px;
  }
  &__title {
    font-size: 2.5rem;
    & > h1 {
      display: inline-block;
      font-size: 100%;
      margin: 0;
    }
    & > a {
      float: right;
      font-size: 1.27rem;
      line-height: 1;
			margin-top: 15px;
    }
  }
	&__group {
		margin: 25px 0;
		position: relative;
		width: 100%;
		&_btn {
			margin-bottom: 0;
		}
	}
	&__label {
		font-size: 1.35rem;
	}
	&__input {
		border: 1px solid #e8e8e8;
		-webkit-box-shadow: inset 1px 1px 0 rgba(0,0,0,.3);
		box-shadow: inset 1px 1px 0 rgba(0,0,0,.3);
		line-height: 30px;
		height: 30px;
		background: #fff;
		font-size: 1.5rem;
		color: rgb(20, 55, 90);
		outline: none;
		padding: 5px 8px;
		width: 100%;
		&_txt {
			min-height: 80px;
		}
		&_checkbox, &_radio {
			margin: 0 6px 0 0;
			padding: 0;
			width: auto;
		}
		&:focus {
			border-color: rgba(5, 69, 153, .3);
			color: #054599;
		}
	}
}

.btn {
  font-size: 1.5rem;
  padding: 3px 6px;
	&:hover {
		cursor: pointer;
	}
}
</style>
