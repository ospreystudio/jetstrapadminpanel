<template>
    <div class="dark-mode">
        <div class="wrapper">

             Preloader
                    <div class="preloader flex-column justify-content-center align-items-center">
                        <img class="animation__wobble" src="../../../storage/app/public/images/AdminLTELogo.png" alt="AdminLTELogo" height="60" width="60">
                    </div>

            <!-- Navbar -->
            <Navbar />
            <!-- /.navbar -->

            <!-- Main Sidebar Container -->
            <Sidebar />

            <!-- Content Wrapper. Contains page content -->
            <div class="content-wrapper">
                <!-- Content Header (Page header) -->
                <div class="content-header">
                    <div class="container-fluid">
                        <div class="row mb-2">
                            <div class="col-sm-6">
                                <slot name="header"></slot>
                            </div><!-- /.col -->
                            <div class="col-sm-6">
                                <ol class="breadcrumb float-sm-right">
                                    <li class="breadcrumb-item"><a href="#">Home</a></li>
                                    <li class="breadcrumb-item active">Dashboard v2</li>
                                </ol>
                            </div><!-- /.col -->
                        </div><!-- /.row -->
                    </div><!-- /.container-fluid -->
                </div>
                <!-- /.content-header -->

                <!-- Main content -->
                <slot></slot>
                <!-- /.content -->
            </div>
            <!-- /.content-wrapper -->


            <Footer />
        </div>
    </div>
</template>

<script>
import Sidebar from '@/components/Sidebar'
import Navbar from '@/components/Navbar'
import Footer from '@/components/footer'
export default {
    name: "Dashboard",
    components: {
        Footer,
        Navbar,
        Sidebar
    },
    mounted() {
      this.init()
    },
    methods: {
        init() {
            let SELECTOR_LOADER = '.loader'
            setTimeout(() =>{
                let $loader = $(SELECTOR_LOADER)
                if($loader) {
                    $loader.css('height', 0)
                    setTimeout(() =>{
                        $loader.children().hide()
                    }, 2000)
                }
            },2000)
        }
    }
}
</script>
