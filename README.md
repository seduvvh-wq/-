            <select id="marjaSelect" required>

                <option value="">اختر المرجع</option>

                <option value="sistani">السيد السيستاني</option>

                <option value="khamenei">السيد الخامنئي</option>

                <option value="fadlallah">السيد فضل الله</option>

            </select>

            <input type="text" placeholder="عنوان المسألة" required>

            <textarea rows="4" placeholder="تفاصيل السؤال..." required></textarea>

            <button type="submit" class="btn-submit">إرسال للمراجعة</button>

        </form>

    </div>

</section>


}

header {

    background: var(--primary);

    color: white;

    text-align: center;

    padding: 40px 20px;

    border-bottom: 5px solid var(--accent);

}

.controls-section {

    background: white;

    padding: 20px;

    position: sticky;

    top: 0;

    box-shadow: 0 2px 10px rgba(0,0,0,0.1);

    z-index: 10;

}const searchInput = document.getElementById('searchInput');

const filterBtns = document.querySelectorAll('.filter-btn');

const fatwaCards = document.querySelectorAll('.fatwa-card');

// وظيفة البحث والفلترة معاً

function updateDisplay() {

    const searchTerm = searchInput.value.toLowerCase();

    const activeFilter = document.querySelector('.filter-btn.active').dataset.filter;

    fatwaCards.forEach(card => {

        const text = card.innerText.toLowerCase();

        const marja = card.dataset.marja;

        

        const matchesSearch = text.includes(searchTerm);

        const matchesFilter = (activeFilter === 'all' || marja === activeFilter);

        if (matchesSearch && matchesFilter) {

            card.style.display = "block";

        } else {

