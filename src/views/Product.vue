<template>
  <div class="product container-fluid">
    <div class="row">
      <div class="col-lg images">
        <div class="images-content">
          <div class="bigger"></div>
          <div class="image-tray">
            <div class="smaller" v-for="n in 6" :key="n"></div>
          </div>
        </div>
      </div>
      <div class="col-lg details">
        <h1>{{ $route.params.product }}</h1>
        <cite>{{ $route.params.product }}</cite>
        <div class="rating">
          <b-form-rating v-model="rating"
                         show-value
                         show-value-max
                         readonly
                         variant="warning"
                         precision="2"></b-form-rating>
        </div>

        <div class="buttons">
          <b-button class="mr-2" variant="primary">
            <b-icon size="" icon="cart-plus-fill" class="mr-1"/> Add to Cart
          </b-button>
          <b-button variant="success">
            <b-icon icon="bag-check-fill" class="mr-1"/> Buy this item
          </b-button>
        </div>

        <div class="description">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit.
          Quisque faucibus pharetra enim, eget ultricies mauris convallis non.
          Nam posuere diam ac purus mattis lobortis.
          Morbi aliquet mauris mi, ac ornare neque suscipit a.
          Nullam efficitur urna a nisl dignissim finibus.
          In venenatis aliquet aliquam.
          Proin nec ipsum in diam malesuada varius.
          Curabitur sagittis condimentum purus.
          Lorem ipsum dolor sit amet, consectetur adipiscing elit.
          Quisque quis eros mi.
          Ut dignissim, lacus et lacinia imperdiet, odio orci scelerisque augue,
          vel accumsan erat elit non libero.
          Cras consequat sapien lectus, vel finibus massa sollicitudin sit amet.
          Aliquam gravida congue tristique.
          Praesent varius egestas metus in tempus.
        </div>

        <div class="options">
          <b-form-group label="Size: " v-slot="{ ariaDescribedby }">
            <b-form-radio-group
              id="radio-group-1"
              v-model="selectedSize"
              :options="sizeOptions"
              :aria-describedby="ariaDescribedby"
              name="radio-options"
            ></b-form-radio-group>
          </b-form-group>

          <b-form-group label="Checkbox: " v-slot="{ ariaDescribedby }">
            <b-form-checkbox-group
              id="checkbox-group-1"
              v-model="selectedCheckbox"
              :options="checkboxOptions"
              :aria-describedby="ariaDescribedby"
              name="radio-options"
            ></b-form-checkbox-group>
          </b-form-group>

          <b-form-group label="Select: " v-slot="{ ariaDescribedby }">
            <b-form-select v-model="selected"
                           :options="selectOptions"
                           :aria-describedby="ariaDescribedby"></b-form-select>
          </b-form-group>
        </div>
      </div>
    </div>

    <div class="row copy-text">
      <div>
        <h2>Just a super Title!</h2>
        <small>Some minor text to match the pattern</small>
      </div>
    </div>

    <div class="container">
      <div class="row">
        <div class="col-lg details">
          <h2>Product details</h2>
          <cite>{{ $route.params.product }}</cite>

          <div class="description">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit.
            Quisque faucibus pharetra enim, eget ultricies mauris convallis non.
            Nam posuere diam ac purus mattis lobortis.
            Morbi aliquet mauris mi, ac ornare neque suscipit a.
            Nullam efficitur urna a nisl dignissim finibus.
            In venenatis aliquet aliquam.
            Proin nec ipsum in diam malesuada varius.
            Curabitur sagittis condimentum purus.
            Lorem ipsum dolor sit amet, consectetur adipiscing elit.
            Quisque quis eros mi.
            Ut dignissim, lacus et lacinia imperdiet, odio orci scelerisque augue,
            vel accumsan erat elit non libero.
            Cras consequat sapien lectus, vel finibus massa sollicitudin sit amet.
            Aliquam gravida congue tristique.
            Praesent varius egestas metus in tempus.
          </div>
        </div>
      </div>
    </div>

    <div class="row image-text">
      <div class="col-lg image"></div>
      <div class="col-lg text">
        <div>
          <h2>Just a super Title!</h2>

          <div class="long-text">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit.
            Quisque faucibus pharetra enim, eget ultricies mauris convallis non.
            Nam posuere diam ac purus mattis lobortis.
            Morbi aliquet mauris mi, ac ornare neque suscipit a.
            Nullam efficitur urna a nisl dignissim finibus.
            In venenatis aliquet aliquam.
            Proin nec ipsum in diam malesuada varius.
            Curabitur sagittis condimentum purus.
            Lorem ipsum dolor sit amet, consectetur adipiscing elit.
            Quisque quis eros mi.
          </div>
        </div>
      </div>
    </div>

    <div class="row image-text">
      <div class="col-lg order-12 order-lg-1 text">
        <div>
          <h2>Just a super Title!</h2>

          <div class="eyebrow"></div>

          <div class="long-text">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit.
            Quisque faucibus pharetra enim, eget ultricies mauris convallis non.
            Nam posuere diam ac purus mattis lobortis.
            Morbi aliquet mauris mi, ac ornare neque suscipit a.
            Nullam efficitur urna a nisl dignissim finibus.
            In venenatis aliquet aliquam.
            Proin nec ipsum in diam malesuada varius.
            Curabitur sagittis condimentum purus.
            Lorem ipsum dolor sit amet, consectetur adipiscing elit.
            Quisque quis eros mi.
          </div>
        </div>
      </div>
      <div class="col-lg order-2 image"></div>
    </div>

  </div>
</template>

<script>
export default {
  name: 'ProductDetail',
  metaInfo() {
    return { title: this.$route.params.product };
  },
  data() {
    return {
      rating: 4,
      selectedSize: 'XS',
      sizeOptions: [
        'XS',
        'S',
        'M',
        'L',
        'XL',
        'XXL',
      ],
      checkboxOptions: [1, 2, 3, 4],
      selectedCheckbox: [1],
      selected: null,
      selectOptions: [
        { value: null, text: 'Please select an option' },
        { value: 'a', text: 'This is First option' },
        { value: 'b', text: 'Selected Option' },
        { value: { C: '3PO' }, text: 'This is an option with object value' },
        { value: 'd', text: 'This one is disabled', disabled: true },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.product {
  background: #F7F7F9;

  h1 {
    text-transform: capitalize;
  }

  .images {
    text-align: right;
    padding: 70px 16px;
    display: flex;
    justify-content: flex-end;
    min-height: 80vh;

    .images-content {
      width: 90%;
      max-width: 700px;

      .bigger {
        width: 100%;
        height: 25vw;
        background: center/cover no-repeat;
        background-image: url(../assets/img.jpg);
        box-shadow: 0 0 7px #00000055;
      }

      .image-tray {
        padding: 7px 0;
        width: 100%;
        overflow: auto;
        white-space:nowrap;

        .smaller {
          width: 192px;
          height: 108px;
          background: center/cover no-repeat;
          background-image: url(../assets/img.jpg);
          display: inline-block;
          margin-right: 7px;

          &:last-child {
            margin-right: 0;
          }
        }
      }
    }
  }

  .details {
    padding: 70px;

    .description {
      margin: 34px 0;
      max-width: 700px;
    }

    .options {
      max-width: 700px;
    }

    .rating {
      width: 200px;
      margin-top: 12px;
    }

    .buttons {
      margin-top: 22px;
    }
  }

  .copy-text {
    background-image: url(../assets/concept.jpg);
  }

  .image-text {
    .image {
      background-image: url(../assets/concept.jpg);
    }
  }

  @media (max-width: 991.98px) {
    .images {
      padding: 25px;
      min-height: 0;

      .images-content {
        width: 100%;

        .bigger {
          display: none;
        }

        .image-tray {
          padding: 0;

          .smaller {
            width: 100%;
            height: 50vh;
          }
        }
      }
    }
    .details {
      padding: 25px;
    }
  }
}
</style>
