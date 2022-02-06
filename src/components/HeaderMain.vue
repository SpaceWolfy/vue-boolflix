<template>
  <div class="header-container">
    <div class="gradient">
      <header>
        <div class="left-cont">
          <img class="logo" src="../assets/Logonetflix.png" alt="" />

          <ul>
            <li>Home</li>
            <li>Serie TV</li>
            <li>Film</li>
            <li>Aggiunti di recente</li>
            <li>La mia lista</li>
          </ul>
        </div>

        <div class="right-cont">
          <div class="search-cont">
            <input v-model="movieKeyWord" class="search-bar" type="text" />
            <button class="search" @click="$emit('search', movieKeyWord)">
              <i class="fas fa-search"></i>
            </button>
          </div>

          <div class="notifications"><i class="fas fa-bell"></i></div>

          <div class="propic">
            <img
              src="https://mir-s3-cdn-cf.behance.net/project_modules/disp/84c20033850498.56ba69ac290ea.png"
              alt=""
            />
            <i class="fas fa-caret-down"></i>
          </div>
        </div>
      </header>

      <div class="jumbotron-info">
        <div class="jumbo-container">
          <img src="../assets/stranger4logo.png" alt="" />

          <div class="jumbo-btns">
            <button class="j-btn"><i class="fas fa-play"></i> Riproduci</button>
            <button class="j-btn">
              <i class="fas fa-plus"></i> La mia lista
            </button>
          </div>

          <div class="trama">
            <h2>Prossimamente su Netflix</h2>
            Un seguito diretto degli eventi della terza stagione, prossimamente
            su Netflix!
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      movieKeyWord: "",
    };
  },
};
</script>

<style lang="scss" scoped>
.header-container {
  background-image: url("../assets/stranger4.jpg");
  height: 650px;
  background-position-y: -400px;
  background-repeat: no-repeat;

  .gradient {
    height: 100%;
    background: linear-gradient(to bottom, transparent 30%, #0c0c0c 99%);
  }

  header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px 55px;
    background: linear-gradient(to bottom, #0c0c0c 3%, transparent 97%);

    .left-cont,
    .right-cont {
      display: flex;
      align-items: center;
    }

    .left-cont {
      ul {
        display: flex;
        list-style: none;
        color: white;
        font-size: 16px;

        li {
          margin: 0 10px;
          cursor: pointer;

          &:hover {
            font-weight: 600;
            margin: 0 9px;
          }
        }
      }

      .logo {
        width: 100px;
        margin-right: 35px;
      }
    }

    .right-cont {
      .search-bar,
      .fas {
        color: white;
      }

      .fas {
        cursor: pointer;
        margin-right: 10px;
      }

      .search-cont {
        .search-bar,
        button {
          background-color: transparent;
          border: none;
        }

        .search-bar {
          height: 20px;
          outline: none;
          width: 120px;
          margin-right: 10px;
          border-bottom: 1px solid white;
        }

        button {
          font-size: 18px;
        }
      }

      .notifications {
        margin: 0 15px 0 20px;
        font-size: 24px;
      }

      .propic {
        display: flex;
        align-items: center;
        width: 32px;
        height: 32px;
        cursor: pointer;

        img {
          width: 100%;
          margin-right: 10px;
        }
      }
    }
  }

  .jumbotron-info {
    margin: 100px 50px;
    .jumbo-container {
      width: 450px;
      height: 600px;

      img {
        width: 90%;
      }

      .j-btn {
        color: white;
        margin: 0 5px;
        background-color: rgba($color: #000000, $alpha: 0.5);
        border: none;
        padding: 12px 35px;
        font-size: 16px;
        border-radius: 3px;
        cursor: pointer;

        .fas {
          margin-right: 5px;
        }
      }

      .trama {
        color: white;
        margin-left: 5px;
        margin-top: 20px;
      }
    }
  }
}
</style>
