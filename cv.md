# My CV

## Name: Erekaikin Vladislav

### Contacts for communication

Telephone: +7-996-619-88-01

Email: pisma.drgn@mail.ru

## About me

I am a 4th year student. The main goal of my training in this course is employment in Epam. I have been creating video content for a long time, and therefore I have experience in design. My main distinguishing features are:

- Quick adaptation
- Punctuality
- Responsible

## My skills:

- Git
- Html
- Css
- JavaScript
- Bootstrap
- Design

## Completed the courses:

### Udemy NodeJs Практический курс(Владилен Минин)

### JavaScript Иван Петриченко

## My projects:

[Food](https://github.com/UchPOchMAchEK/learnJS_Food.git)

[CoursesShop](https://github.com/UchPOchMAchEK/CoursesShop.git)

[GloAcademy-lesson](https://github.com/UchPOchMAchEK/GloAcademy-lesson.git)

## Level of English A2

### My experience of using English: Working at the 2018 FIFA World Cup

## Example code:

```
//Глобальный обработчик событий
window.addEventListener('DOMContentLoaded', () => {
    const tabs = document.querySelectorAll('.tabheader__item'), //Вкладки
        tabsContent = document.querySelectorAll('.tabcontent'), //Контент
        tabsParent = document.querySelector('.tabheader__items'); //Блок вкладок

    //Скрытие ненужного контента
    function hideTabContent() {
        tabsContent.forEach(item => {
            item.classList.add('hide');
            item.classList.remove('show');
        });

        //Изменение классов активности
        tabs.forEach(item => {
            item.classList.remove('tabheader__item_active');
        });
    }

    //Отображение контента
    function showTabContent(i = 0) {
        tabsContent[i].classList.add('show');
        tabsContent[i].classList.remove('hide');
        tabs[i].classList.add('tabheader__item_active');
    }

    hideTabContent();
    showTabContent();

    //Обработчик событий клика
    tabsParent.addEventListener('click', (event) => {
        const target = event.target;

        //Проверка на попадание в tab
        if (target && target.classList.contains('tabheader__item')) {
            tabs.forEach((item, i) => {
                if (target == item) {
                    hideTabContent();
                    showTabContent(i);
                }
            });
        }
    });

    //Таймер
    const deadline = '2021-05-11';

    function getTimeRemaining(endtime) {
        const t = Date.parse(endtime) - Date.parse(new Date()),
            days = Math.floor(t / (1000 * 60 * 60 * 24)),
            hours = Math.floor((t / (1000 * 60 * 60) % 24)),
            minutes = Math.floor((t / 1000 / 60) % 60),
            seconds = Math.floor((t / 1000) % 60);

        return {
            'total': t,
            'days': days,
            'hours': hours,
            'minutes': minutes,
            'seconds': seconds
        };
    }

    function getZero(num) {
        if(num >= 0 && num < 10) {
            return `0${num}`;
        } else {
            return num;
        }
    }

    function setClock(selector, endtime) {
        const timer = document.querySelector(selector),
            days = timer.querySelector('#days'),
            hours = timer.querySelector('#hours'),
            minutes = timer.querySelector('#minutes'),
            seconds = timer.querySelector('#seconds'),
            timeInterval = setInterval(updateClock, 1000);

        updateClock();

        function updateClock() {
            const t = getTimeRemaining(endtime);

            days.innerHTML = getZero(t.days);
            hours.innerHTML = getZero(t.hours);
            minutes.innerHTML = getZero(t.minutes);
            seconds.innerHTML = getZero(t.seconds);

            if (t.total <= 0){
                clearInterval(timeInterval);
            }
        }
    }

    setClock('.timer', deadline);
    });
```
