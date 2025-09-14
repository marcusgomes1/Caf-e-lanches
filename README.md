<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Café & Lanches - Ondina, Salvador</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css" rel="stylesheet">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.8.1/font/bootstrap-icons.css">
    <style>
        :root {
            --cafe-color: #6f4e37;
            --lanche-color: #d4a76a;
            --accent-color: #c0a080;
            --dark-color: #3e2723;
            --light-color: #f9f5eb;
            --salvador-blue: #0073e6;
            --salvador-white: #f5f5f5;
        }
        
        body {
            background-color: var(--salvador-white);
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            color: #333;
        }
        
        .navbar {
            background-color: var(--cafe-color);
        }
        
        .btn-cafe {
            background-color: var(--cafe-color);
            border-color: var(--dark-color);
            color: white;
        }
        
        .btn-lanche {
            background-color: var(--lanche-color);
            border-color: var(--dark-color);
            color: white;
        }
        
        .btn-salvador {
            background-color: var(--salvador-blue);
            color: white;
        }
        
        .btn-cafe:hover, .btn-lanche:hover, .btn-salvador:hover {
            background-color: var(--dark-color);
            color: white;
        }
        
        .hero-section {
            background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url('https://images.unsplash.com/photo-1554118811-1e0d58224f24?ixlib=rb-4.0.3&auto=format&fit=crop&w=1350&q=80');
            background-size: cover;
            background-position: center;
            color: white;
            padding: 100px 0;
            margin-bottom: 30px;
            position: relative;
        }
        
        .location-badge {
            position: absolute;
            top: 20px;
            right: 20px;
            background-color: var(--salvador-blue);
            color: white;
            padding: 10px 15px;
            border-radius: 30px;
            font-weight: bold;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }
        
        .card-product {
            transition: transform 0.3s;
            margin-bottom: 20px;
            border: none;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            height: 100%;
            border-radius: 10px;
            overflow: hidden;
        }
        
        .card-product:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
        }
        
        .category-badge {
            position: absolute;
            top: 10px;
            left: 10px;
            padding: 5px 10px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: bold;
        }
        
        .badge-cafe {
            background-color: var(--cafe-color);
            color: white;
        }
        
        .badge-lanche {
            background-color: var(--lanche-color);
            color: white;
        }
        
        .price-tag {
            font-weight: bold;
            color: var(--cafe-color);
            font-size: 1.2rem;
        }
        
        footer {
            background-color: var(--dark-color);
            color: white;
            padding: 40px 0;
            margin-top: 50px;
        }
        
        .category-filter {
            margin-bottom: 30px;
        }
        
        .category-btn {
            margin: 5px;
        }
        
        .cart-preview {
            position: fixed;
            bottom: 20px;
            right: 20px;
            z-index: 1000;
        }
        
        .section-title {
            position: relative;
            padding-bottom: 15px;
            margin-bottom: 30px;
            font-weight: bold;
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 60px;
            height: 3px;
            background-color: var(--cafe-color);
        }
        
        .coffee-icon {
            color: var(--accent-color);
            font-size: 1.5rem;
            margin-right: 5px;
        }
        
        .location-section {
            background-color: #f8f9fa;
            padding: 60px 0;
            border-radius: 10px;
        }
        
        .salvador-theme {
            color: var(--salvador-blue);
            font-weight: bold;
        }
        
        .map-container {
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            height: 300px;
        }
        
        .testimonial-card {
            border-left: 4px solid var(--cafe-color);
            padding-left: 20px;
        }
    </style>
</head>
<body>
    <!-- Navbar -->
    <nav class="navbar navbar-expand-lg navbar-dark">
        <div class="container">
            <a class="navbar-brand" href="#">
                <i class="bi bi-cup-hot-fill coffee-icon"></i> Café & Lanches
            </a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNav">
                <ul class="navbar-nav me-auto">
                    <li class="nav-item">
                        <a class="nav-link active" href="#">Início</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#cardapio">Cardápio</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#localizacao">Localização</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#sobre">Sobre</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#contato">Contato</a>
                    </li>
                </ul>
                <div class="d-flex">
                    <a href="#" class="btn btn-outline-light me-2" data-bs-toggle="modal" data-bs-target="#cartModal">
                        <i class="bi bi-cart"></i> <span class="badge bg-danger" id="cart-count">0</span>
                    </a>
                    <a href="#pedido" class="btn btn-light">
                        <i class="bi bi-whatsapp"></i> Fazer Pedido
                    </a>
                </div>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero-section text-center">
        <div class="location-badge">
            <i class="bi bi-geo-alt"></i> Ondina, Salvador
        </div>
        <div class="container">
            <h1 class="display-4 fw-bold">Café & Lanches</h1>
            <p class="lead">Os melhores cafés e lanches com sabor baiano</p>
            <p class="mb-4">Localizado na Avenida Milton Santos, no coração de Ondina</p>
            <a href="#cardapio" class="btn btn-cafe btn-lg me-2">Ver Cardápio</a>
            <a href="#pedido" class="btn btn-lanche btn-lg">Fazer Pedido</a>
        </div>
    </section>

    <!-- Main Content -->
    <div class="container">
        <!-- Category Filter -->
        <div class="category-filter text-center" id="cardapio">
            <h2 class="section-title">Cardápio</h2>
            <div class="btn-group" role="group">
                <button type="button" class="btn btn-outline-primary active category-btn" data-category="todos">Todos</button>
                <button type="button" class="btn btn-outline-primary category-btn" data-category="cafe">Cafés</button>
                <button type="button" class="btn btn-outline-primary category-btn" data-category="lanche">Lanches</button>
                <button type="button" class="btn btn-outline-primary category-btn" data-category="doce">Doces</button>
                <button type="button" class="btn btn-outline-primary category-btn" data-category="baiano">Sabores Baianos</button>
            </div>
        </div>

        <!-- Products Grid -->
        <div class="row" id="products-grid">
            <!-- Café 1 -->
            <div class="col-md-4 mb-4 product-item" data-category="cafe">
                <div class="card card-product">
                    <span class="category-badge badge-cafe">Café</span>
                    <img src="https://images.unsplash.com/photo-1495474472287-4d71bcdd2085?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80" class="card-img-top" alt="Café Expresso">
                    <div class="card-body">
                        <h5 class="card-title">Café Expresso</h5>
                        <p class="card-text">Café espresso tradicional, forte e encorpado.</p>
                        <div class="d-flex justify-content-between align-items-center">
                            <span class="price-tag">R$ 5,90</span>
                            <button class="btn btn-cafe add-to-cart" data-product="Café Expresso" data-price="5.90">Adicionar</button>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- Café Baiano -->
            <div class="col-md-4 mb-4 product-item" data-category="cafe baiano">
                <div class="card card-product">
                    <span class="category-badge badge-cafe">Café Baiano</span>
                    <img src="https://images.unsplash.com/photo-1572442388796-11668a67e53d?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80" class="card-img-top" alt="Café com Coco">
                    <div class="card-body">
                        <h5 class="card-title">Café com Coco</h5>
                        <p class="card-text">Café especial com toque de coco baiano.</p>
                        <div class="d-flex justify-content-between align-items-center">
                            <span class="price-tag">R$ 8,90</span>
                            <button class="btn btn-cafe add-to-cart" data-product="Café com Coco" data-price="8.90">Adicionar</button>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- Lanche Baiano -->
            <div class="col-md-4 mb-4 product-item" data-category="lanche baiano">
                <div class="card card-product">
                    <span class="category-badge badge-lanche">Lanche Baiano</span>
                    <img src="https://images.unsplash.com/photo-1551782450-a2132b4ba21d?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80" class="card-img-top" alt="Acarajé">
                    <div class="card-body">
                        <h5 class="card-title">Acarajé</h5>
                        <p class="card-text">Acarajé tradicional baiano com vatapá e camarão.</p>
                        <div class="d-flex justify-content-between align-items-center">
                            <span class="price-tag">R$ 12,90</span>
                            <button class="btn btn-lanche add-to-cart" data-product="Acarajé" data-price="12.90">Adicionar</button>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- Lanche 2 -->
            <div class="col-md-4 mb-4 product-item" data-category="lanche">
                <div class="card card-product">
                    <span class="category-badge badge-lanche">Lanche</span>
                    <img src="https://images.unsplash.com/photo-1481070414801-51fd732d7184?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80" class="card-img-top" alt="Sanduíche Natural">
                    <div class="card-body">
                        <h5 class="card-title">Sanduíche Natural</h5>
                        <p class="card-text">Pão integral, frango, cream cheese e vegetais.</p>
                        <div class="d-flex justify-content-between align-items-center">
                            <span class="price-tag">R$ 16,90</span>
                            <button class="btn btn-lanche add-to-cart" data-product="Sanduíche Natural" data-price="16.90">Adicionar</button>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- Doce Baiano -->
            <div class="col-md-4 mb-4 product-item" data-category="doce baiano">
                <div class="card card-product">
                    <span class="category-badge" style="background-color: #dc3545;">Doce Baiano</span>
                    <img src="https://images.unsplash.com/photo-1587314168485-3236d6710814?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80" class="card-img-top" alt="Cocada">
                    <div class="card-body">
                        <h5 class="card-title">Cocada Baiana</h5>
                        <p class="card-text">Cocada tradicional baiana, doce e saborosa.</p>
                        <div class="d-flex justify-content-between align-items-center">
                            <span class="price-tag">R$ 7,90</span>
                            <button class="btn btn-cafe add-to-cart" data-product="Cocada Baiana" data-price="7.90">Adicionar</button>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- Doce 2 -->
            <div class="col-md-4 mb-4 product-item" data-category="doce">
                <div class="card card-product">
                    <span class="category-badge" style="background-color: #dc3545;">Doce</span>
                    <img src="https://images.unsplash.com/photo-1499636136210-6f4ee915583e?ixlib=rb-4.0.3&auto=format&fit=crop&w=500&q=80" class="card-img-top" alt="Croissant">
                    <div class="card-body">
                        <h5 class="card-title">Croissant Doce</h5>
                        <p class="card-text">Croissant folhado com recheio de chocolate.</p>
                        <div class="d-flex justify-content-between align-items-center">
                            <span class="price-tag">R$ 7,90</span>
                            <button class="btn btn-cafe add-to-cart" data-product="Croissant Doce" data-price="7.90">Adicionar</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Location Section -->
        <section id="localizacao" class="location-section my-5 py-5">
            <div class="row">
                <div class="col-lg-6">
                    <h2 class="section-title">Nossa Localização</h2>
                    <p class="salvador-theme">Estamos localizados no coração de Ondina, Salvador</p>
                    <p><i class="bi bi-geo-alt-fill"></i> <strong>Endereço:</strong> Avenida Milton Santos, 123 - Ondina, Salvador - BA</p>
                    <p><i class="bi bi-clock"></i> <strong>Horário de Funcionamento:</strong></p>
                    <ul>
                        <li>Segunda a Sexta: 7h às 20h</li>
                        <li>Sábados: 8h às 18h</li>
                        <li>Domingos: 9h às 16h</li>
                    </ul>
                    <p><i class="bi bi-telephone"></i> <strong>Telefone:</strong> (71) 3333-4444</p>
                    <p><i class="bi bi-whatsapp"></i> <strong>WhatsApp:</strong> (71) 99999-8888</p>
                    
                    <div class="mt-4">
                        <a href="https://wa.me/5571999998888?text=Olá! Gostaria de fazer um pedido." class="btn btn-success me-2">
                            <i class="bi bi-whatsapp"></i> Pedir pelo WhatsApp
                        </a>
                        <a href="https://maps.google.com/?q=Avenida Milton Santos, 123, Ondina, Salvador, BA" class="btn btn-salvador">
                            <i class="bi bi-map"></i> Como chegar
                        </a>
                    </div>
                </div>
                <div class="col-lg-6">
                    <div class="map-container">
                        <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3887.269282693674!2d-38.510583!3d-13.004582!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x716037ca23ca5b3%3A0x1b9fc4ff0c2d7d1!2sAv.%20Milton%20Santos%20-%20Ondina%2C%20Salvador%20-%20BA!5e0!3m2!1spt-BR!2sbr!4v1653573957297!5m2!1spt-BR!2sbr" width="100%" height="100%" style="border:0;" allowfullscreen="" loading="lazy"></iframe>
                    </div>
                </div>
            </div>
        </section>

        <!-- About Section -->
        <section id="sobre" class="my-5 py-5 border-top">
            <div class="row">
                <div class="col-lg-6">
                    <h2 class="section-title">Sobre Nós</h2>
                    <p>O Café & Lanches nasceu da paixão por cafés especiais e lanches saborosos com um toque baiano. Nossa missão é proporcionar momentos especiais através de produtos de alta qualidade.</p>
                    <p>Localizados na Avenida Milton Santos, no vibrante bairro de Ondina em Salvador, buscamos oferecer o melhor da gastronomia baiana com um toque contemporâneo.</p>
                    <p>Utilizamos grãos de café selecionados e ingredientes frescos para preparar tudo com carinho e cuidado, sempre valorizando os sabores locais.</p>
                    <p>Venha nos visitar e desfrutar do melhor café de Salvador!</p>
                </div>
                <div class="col-lg-6">
                    <img src="https://images.unsplash.com/photo-1442512595331-e89e73853f31?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" class="img-fluid rounded" alt="Nossa loja">
                </div>
            </div>
        </section>

        <!-- Testimonials Section -->
        <section class="my-5 py-5 border-top">
            <h2 class="section-title">O que Nossos Clientes Dizem</h2>
            <div class="row">
                <div class="col-md-4 mb-4">
                    <div class="testimonial-card">
                        <p>"Melhor café da região! O acarajé é simplesmente divino, me lembra o da minha avó."</p>
                        <p class="salvador-theme">- Maria Silva, Ondina</p>
                    </div>
                </div>
                <div class="col-md-4 mb-4">
                    <div class="testimonial-card">
                        <p>"Adoro vir aqui estudar. O ambiente é aconchegante e o café com coco é minha paixão."</p>
                        <p class="salvador-theme">- João Santos, Estudante da UFBA</p>
                    </div>
                </div>
                <div class="col-md-4 mb-4">
                    <div class="testimonial-card">
                        <p>"Sou cliente fiel! Sempre que estou passando por Ondina, paro para tomar um café."</p>
                        <p class="salvador-theme">- Carlos Oliveira, Empresário</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Contact Section -->
        <section id="contato" class="my-5 py-5 border-top">
            <h2 class="section-title">Entre em Contato</h2>
            <div class="row">
                <div class="col-md-6">
                    <form>
                        <div class="mb-3">
                            <label for="name" class="form-label">Nome</label>
                            <input type="text" class="form-control" id="name" required>
                        </div>
                        <div class="mb-3">
                            <label for="email" class="form-label">Email</label>
                            <input type="email" class="form-control" id="email" required>
                        </div>
                        <div class="mb-3">
                            <label for="message" class="form-label">Mensagem</label>
                            <textarea class="form-control" id="message" rows="4" required></textarea>
                        </div>
                        <button type="submit" class="btn btn-cafe">Enviar Mensagem</button>
                    </form>
                </div>
                <div class="col-md-6">
                    <div class="card">
                        <div class="card-body">
                            <h5 class="card-title">Informações de Contato</h5>
                            <p><i class="bi bi-geo-alt"></i> Avenida Milton Santos, 123 - Ondina, Salvador - BA</p>
                            <p><i class="bi bi-telephone"></i> (71) 3333-4444</p>
                            <p><i class="bi bi-whatsapp"></i> (71) 99999-8888</p>
                            <p><i class="bi bi-envelope"></i> contato@cafeondina.com.br</p>
                            <h6>Horário de Funcionamento</h6>
                            <p>Segunda a Sexta: 7h às 20h</p>
                            <p>Sábado: 8h às 18h</p>
                            <p>Domingo: 9h às 16h</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- Cart Preview -->
    <div class="cart-preview">
        <button class="btn btn-cafe btn-lg rounded-pill" data-bs-toggle="modal" data-bs-target="#cartModal">
            <i class="bi bi-cart"></i> <span class="badge bg-danger" id="cart-preview-count">0</span>
        </button>
    </div>

    <!-- Cart Modal -->
    <div class="modal fade" id="cartModal" tabindex="-1">
        <div class="modal-dialog modal-lg">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title">Seu Carrinho</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>
                <div class="modal-body">
                    <table class="table">
                        <thead>
                            <tr>
                                <th>Produto</th>
                                <th>Quantidade</th>
                                <th>Preço</th>
                                <th>Total</th>
                                <th></th>
                            </tr>
                        </thead>
                        <tbody id="cart-items">
                            <!-- Itens do carrinho serão inseridos aqui -->
                        </tbody>
                        <tfoot>
                            <tr>
                                <td colspan="3" class="text-end"><strong>Total:</strong></td>
                                <td><strong id="cart-total">R$ 0,00</strong></td>
                                <td></td>
                            </tr>
                        </tfoot>
                    </table>
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Continuar Comprando</button>
                    <button type="button" class="btn btn-cafe" id="checkout-btn">Finalizar Pedido</button>
                </div>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="row">
                <div class="col-md-4">
                    <h5>Café & Lanches</h5>
                    <p>Os melhores cafés e lanches com sabor baiano.</p>
                    <p>Avenida Milton Santos, 123 - Ondina, Salvador - BA</p>
                </div>
                <div class="col-md-4">
                    <h5>Links Rápidos</h5>
                    <ul class="list-unstyled">
                        <li><a href="#" class="text-white">Início</a></li>
                        <li><a href="#cardapio" class="text-white">Cardápio</a></li>
                        <li><a href="#localizacao" class="text-white">Localização</a></li>
                        <li><a href="#sobre" class="text-white">Sobre</a></li>
                        <li><a href="#contato" class="text-white">Contato</a></li>
                    </ul>
                </div>
                <div class="col-md-4">
                    <h5>Redes Sociais</h5>
                    <div class="d-flex gap-3 mb-3">
                        <a href="#" class="text-white"><i class="bi bi-facebook fs-4"></i></a>
                        <a href="#" class="text-white"><i class="bi bi-instagram fs-4"></i></a>
                        <a href="#" class="text-white"><i class="bi bi-whatsapp fs-4"></i></a>
                    </div>
                    <h5>Formas de Pagamento</h5>
                    <div class="d-flex gap-2">
                        <span class="badge bg-light text-dark">Dinheiro</span>
                        <span class="badge bg-light text-dark">Cartão</span>
                        <span class="badge bg-light text-dark">PIX</span>
                    </div>
                </div>
            </div>
            <div class="row mt-3">
                <div class="col text-center">
                    <p>&copy; 2023 Café & Lanches - Ondina, Salvador. Todos os direitos reservados.</p>
                </div>
            </div>
        </div>
    </footer>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/js/bootstrap.bundle.min.js"></script>
    <script>
        // Carrinho de compras
        let cart = [];
        
        document.addEventListener('DOMContentLoaded', function() {
            // Filtro de categorias
            const filterButtons = document.querySelectorAll('.category-btn');
            filterButtons.forEach(button => {
                button.addEventListener('click', function() {
                    const category = this.getAttribute('data-category');
                    
                    filterButtons.forEach(btn => btn.classList.remove('active'));
                    this.classList.add('active');
                    
                    filterProducts(category);
                });
            });
            
            // Adicionar ao carrinho
            const addToCartButtons = document.querySelectorAll('.add-to-cart');
            addToCartButtons.forEach(button => {
                button.addEventListener('click', function() {
                    const product = this.getAttribute('data-product');
                    const price = parseFloat(this.getAttribute('data-price'));
                    
                    addToCart(product, price);
                    updateCartUI();
                    
                    // Feedback visual
                    this.innerHTML = 'Adicionado!';
                    setTimeout(() => {
                        this.innerHTML = 'Adicionar';
                    }, 1500);
                });
            });
            
            // Finalizar pedido
            document.getElementById('checkout-btn').addEventListener('click', function() {
                if (cart.length > 0) {
                    // Gerar mensagem para WhatsApp
                    let message = "Olá! Gostaria de fazer um pedido:%0A";
                    cart.forEach(item => {
                        message += `- ${item.quantity}x ${item.product} (R$ ${(item.price * item.quantity).toFixed(2)})%0A`;
                    });
                    message += `%0ATotal: R$ ${calculateTotal().toFixed(2)}`;
                    
                    // Abrir WhatsApp
                    window.open(`https://wa.me/5571999998888?text=${message}`, '_blank');
                    
                    // Limpar carrinho
                    cart = [];
                    updateCartUI();
                    const cartModal = bootstrap.Modal.getInstance(document.getElementById('cartModal'));
                    cartModal.hide();
                } else {
                    alert('Seu carrinho está vazio!');
                }
            });
            
            // Inicializar UI do carrinho
            updateCartUI();
        });
        
        function filterProducts(category) {
            const products = document.querySelectorAll('.product-item');
            
            products.forEach(product => {
                if (category === 'todos' || product.getAttribute('data-category').includes(category)) {
                    product.style.display = 'block';
                } else {
                    product.style.display = 'none';
                }
            });
        }
        
        function addToCart(product, price) {
            // Verificar se o produto já está no carrinho
            const existingItem = cart.find(item => item.product === product);
            
            if (existingItem) {
                existingItem.quantity++;
            } else {
                cart.push({
                    product: product,
                    price: price,
                    quantity: 1
                });
            }
        }
        
        function calculateTotal() {
            return cart.reduce((total, item) => total + (item.price * item.quantity), 0);
        }
        
        function updateCartUI() {
            const cartItems = document.getElementById('cart-items');
            const cartTotal = document.getElementById('cart-total');
            const cartCount = document.getElementById('cart-count');
            const cartPreviewCount = document.getElementById('cart-preview-count');
            
            // Limpar itens do carrinho
            cartItems.innerHTML = '';
            
            // Calcular total
            let total = calculateTotal();
            
            // Adicionar itens ao carrinho
            cart.forEach(item => {
                const itemTotal = item.price * item.quantity;
                
                const row = document.createElement('tr');
                row.innerHTML = `
                    <td>${item.product}</td>
                    <td>
                        <div class="input-group input-group-sm" style="width: 90px;">
                            <button class="btn btn-outline-secondary decrease-quantity" data-product="${item.product}">-</button>
                            <input type="number" class="form-control text-center" value="${item.quantity}" min="1" readonly>
                            <button class="btn btn-outline-secondary increase-quantity" data-product="${item.product}">+</button>
                        </div>
                    </td>
                    <td>R$ ${item.price.toFixed(2)}</td>
                    <td>R$ ${itemTotal.toFixed(2)}</td>
                    <td><button class="btn btn-sm btn-danger remove-item" data-product="${item.product}"><i class="bi bi-trash"></i></button></td>
                `;
                
                cartItems.appendChild(row);
            });
            
            // Atualizar total
            cartTotal.textContent = `R$ ${total.toFixed(2)}`;
            
            // Atualizar contador
            const itemCount = cart.reduce((sum, item) => sum + item.quantity, 0);
            cartCount.textContent = itemCount;
            cartPreviewCount.textContent = itemCount;
            
            // Adicionar event listeners para os botões de quantidade e remoção
            document.querySelectorAll('.increase-quantity').forEach(button => {
                button.addEventListener('click', function() {
                    const product = this.getAttribute('data-product');
                    const item = cart.find(item => item.product === product);
                    item.quantity++;
                    updateCartUI();
                });
            });
            
            document.querySelectorAll('.decrease-quantity').forEach(button => {
                button.addEventListener('click', function() {
                    const product = this.getAttribute('data-product');
                    const item = cart.find(item => item.product === product);
                    
                    if (item.quantity > 1) {
                        item.quantity--;
                    } else {
                        cart = cart.filter(item => item.product !== product);
                    }
                    
                    updateCartUI();
                });
            });
            
            document.querySelectorAll('.remove-item').forEach(button => {
                button.addEventListener('click', function() {
                    const product = this.getAttribute('data-product');
                    cart = cart.filter(item => item.product !== product);
                    updateCartUI();
                });
            });
        }
    </script>
</body>
</html>
