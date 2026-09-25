<style>
    .carousels-wrapper {
        width: 100%;
        margin: 20px 0;
    }

    .carousel {
        width: 100%;
        overflow: hidden;
        mask-image: linear-gradient(to right, transparent, #000 10% 90%, transparent);
        -webkit-mask-image: linear-gradient(to right, transparent, #000 10% 90%, transparent);
    }

    .track {
        display: flex;
        width: max-content;
        will-change: transform;
        animation: scroll 15s linear infinite;
    }

    @keyframes scroll {
        0% {
            transform: translateX(0);
        }
        100% {
            transform: translateX(-50%);
        }
    }

    .item {
        width: 240px;
        height: 160px;
        flex-shrink: 0;
        border-radius: 12px;
        margin-right: 15px;
        overflow: hidden;
        transition: transform 0.3s ease;
    }

    .item img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        display: block;
        transition: filter 0.3s ease, transform 0.3s ease;
        backface-visibility: hidden;
    }

    /* Grayscale out items when hovering the carousel */
    .carousel:hover .item img {
        filter: grayscale(0.8);
    }

    /* Highlight hovered item */
    .item:hover img {
        filter: grayscale(0) !important;
        transform: scale(1.05);
    }

    /* Pause animation on hover */
    .carousel:hover .track {
        animation-play-state: paused;
    }

    /* Responsive adjustments */
    @media (max-width: 760px) {
        .item {
            width: 180px;
            height: 120px;
            margin-right: 12px;
        }
    }

    @media (max-width: 480px) {
        .carousel {
            mask-image: linear-gradient(to right, transparent, #000 5% 95%, transparent);
            -webkit-mask-image: linear-gradient(to right, transparent, #000 5% 95%, transparent);
        }

        .item {
            width: 140px;
            height: 95px;
            margin-right: 10px;
        }
    }
</style>

<div class="carousels-wrapper">
    <div class="carousel">
        <div class="track">
            <!-- First Set -->
            <div class="item"><img src="YOUR_IMAGE_URL_1" alt="Certificate 1"></div>
            <div class="item"><img src="YOUR_IMAGE_URL_2" alt="Certificate 2"></div>
            <div class="item"><img src="YOUR_IMAGE_URL_3" alt="Certificate 3"></div>
            <div class="item"><img src="YOUR_IMAGE_URL_4" alt="Certificate 4"></div>

            <!-- Exact Duplicate Set (Required for continuous animation) -->
            <div class="item"><img src="YOUR_IMAGE_URL_1" alt="Certificate 1"></div>
            <div class="item"><img src="YOUR_IMAGE_URL_2" alt="Certificate 2"></div>
            <div class="item"><img src="YOUR_IMAGE_URL_3" alt="Certificate 3"></div>
            <div class="item"><img src="YOUR_IMAGE_URL_4" alt="Certificate 4"></div>
        </div>
    </div>
</div>
