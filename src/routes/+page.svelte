<script>
    // Zde případně logika
</script>

<main>
    <div class="Main-Container">
        <h1>Vysvětlení</h1>
        <p>Tato stránka je pouze pro vzdělávací účely. Tvořím toto protože si chci procvičit svoje skill a zároveň se tím učit i ty předměty na maturitu.</p>
        <p>Všechny soubory, poznámky jsou buď z mé hlavy nebo spíše od učitelů a jejich zápisků nebo dokumentů.</p>
        <p>Zde na hlavní stránce toho moc nenajdete, spíš už se běžte učit.</p>
        <p>Jsem Marat a chodím/chodil jsem na SOUEPL.</p>
    </div>
</main>

<style>
    main {
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 32px;
        min-height: 80vh;
        background: linear-gradient(to bottom right, #f8f9fa, #e9ecef);
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }

    .Main-Container {
        background-color: white;
        padding: 32px 48px;
        border-radius: 12px;
        box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
        max-width: 800px;
        width: 100%;
        color: #333;
    }

    h1 {
        font-size: 40px;
        margin-bottom: 16px;
        color: #0077cc;
        text-align: center;
    }

    p {
        font-size: 18px;
        line-height: 28px;
        margin-bottom: 16px;
    }

    @media (max-width: 600px) {
        .Main-Container {
            padding: 24px 24px;
        }

        h1 {
            font-size: 32px;
        }

        p {
            font-size: 16px;
            line-height: 24px;
        }
    }
</style>
