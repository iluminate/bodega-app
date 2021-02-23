<template>
  <div class="content-wrapper" style="min-height: 229px;">
    <!-- Content Header (Page header) -->
    <div class="content-header">
      <div class="container-fluid">
        <div class="row mb-2">
          <div class="col-sm-6">
            <h1 class="m-0">Productos</h1>
          </div><!-- /.col -->
          <div class="col-sm-6">
            <ol class="breadcrumb float-sm-right">
              <li class="breadcrumb-item"><a href="#">Home</a></li>
              <li class="breadcrumb-item active">Productos</li>
            </ol>
          </div><!-- /.col -->
        </div><!-- /.row -->
      </div><!-- /.container-fluid -->
    </div>
    <!-- /.content-header -->

    <!-- Main content -->
    <section class="content">
      <div class="container-fluid">
        <!-- Small boxes (Stat box) -->


        <div class="row">
          <div class="col-lg-12 col-12">
            <div class="card">

              <div class="card-body p-0">
                <table class="table table-striped">
                  <thead>
                  <tr>

                    <th style="width: 10px">#</th>
                    <th>Descripcion</th>
                    <th>Precio de compra</th>
                    <th>Precio de venta</th>
                    <th>Categoria</th>
                    <th>Marca</th>
                    <th>Proveedor</th>
                    <th>Unidades</th>
                    <th>Acciones</th>

                  </tr>
                  </thead>
                  <tbody>
                  <tr v-for="product of products">
                    <td>
                      {{product.product_id}}
                    </td>
                    <td>
                      {{product.product_description}}
                    </td>
                    <td>
                      {{product.purchase_price}}
                    </td>
                    <td>
                      {{product.sale_price}}
                    </td>
                    <td>
                      {{product.category}}
                    </td>
                    <td>
                      {{product.brand}}
                    </td>
                    <td>
                      {{product.product_provider}}
                    </td>
                    <td>
                      {{product.units}}
                    </td>

                    <td>

                      <button type="button" class="btn btn-outline-info btn-sm"><i class="fas fa-edit"></i></button>
                      <button type="button" class="btn btn-sm btn-outline-danger"><i class="far fa-trash-alt"></i></button>
                    </td>
                  </tr>

                  </tbody>

                </table>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    </div>
</template>

<script>
export default {
  layout: 'adminLte',
  components: {},

  data() {
    return {
      products: [
        {
          "product_id": "1",
          "product_description": "Leche",
          "purchase_price": 1.80,
          "sale_price": 2.30,
          "category": "Abarrotes",
          "brand": "Gloria",
          "product_provider": "Yichang S.A.",
          "units": "L"
        }
      ]
    }
  },

  async fetch() {
    this.products = await fetch(
      'http://localhost:8080/api/v1/products'
    ).then(res => res.json())
    console.log(products);
  }

}

</script>

<style>
</style>
