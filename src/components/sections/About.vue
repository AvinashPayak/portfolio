<template>
    <div>
        <div class="content">
            <div class="total-exp">
                <span>3+</span>
                <p>years of working experience</p>
            </div>
            <div class="info">
                <div>
                    <img src="../icons/office.svg" alt="work" width="50">
                    <h2>Experience</h2>
                    <p>2+ years of fullstack development experience and 1+ years of QA experience</p>
                </div>
                <div>
                    <img src="../icons/content-writer.svg" alt="content-writer" width="50">
                    <h2>Extracurricular</h2>
                    <p>8 Articles published as content writer for CSI's magazine (2017-19)</p>
                </div>
                <div>
                    <img src="../icons/location.svg" alt="location" width="50">
                    <h2>Location</h2>
                    <p>Currently located in Mumbai</p>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>

.about .content {
    grid-column: 2/12;
    grid-row: 1/1;
    display: flex;
    position: relative;
}

.info {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: 1fr;
    column-gap: 3rem;
    padding: 2rem;
}

.total-exp {
    background-color: steelblue;
    display: flex;
    flex-direction: column;
    padding: 1rem 3rem;
    position: relative;
    top: 3rem;
    color: white;
}

.info h2 {
    font-size: 24px;
    font-weight: 900;
}

.info p {
    font-size: 16px;
}

.total-exp span {
    font-size: 60px;
}

.total-exp p {
    font-size: 16px;
}
</style>