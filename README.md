# Ты не сможешь скрыться от меня или как взломать чужую программу

Как-то раз мне очень захотелось воспользоваться одной программой. Я нашла её, открыла, а таааам...

![1](https://github.com/ludmilastemp/Crack/assets/138589010/4c3781dd-ab74-4d1d-9215-a04a11e4b354)

## Шок!!!

Я удивилась. 1234... 1111... пароль... Но результат только один 

![2](https://github.com/ludmilastemp/Crack/assets/138589010/d9bd21f2-4642-464c-969f-b92299018495)

Короче говоря, мне ничего не помогало. Но я быстро нашла человека, который поставил этот пароль. Им оказался https://github.com/SeveraTheDuck. Недолго думая, я пошла к нему. В комнате его не было, на кухне тоже, нигде его нет. Пришлось импровизировать...

Я вернулась в свою комнату и села за ноутбук. Открыла DOSbox и начала вспоминать, чему меня учил Дед. td, ctrl+enter, enter. Здравствуй, любимый турбо дебагер. F7 F7 F7 F7 и много много F7.

## Первый взлом

Хорошо, есть 2 функции, они довольно стандартные. Одна вводит пароль, другая обрабатывает. Окей. Но где проверка переполнения буфера? Вау, ее нет. Вот ты и попался. Нажимаю '0' 20 раз. Доступ запрещен.
Еще один проход в td... Так вот оно что, ты единицу прибавляешь, ладно. **'0' 10 раз**, **'1' 10 раз**, **enter**. 

![3](https://github.com/ludmilastemp/Crack/assets/138589010/cdf27009-ad8e-4248-ad52-900581b6b26c)

## Второй взлом

Ураааа. Но погодите, так не интересно, слишком легко. td выручай. Еще 20 минут просмотра кода. Все нормально, но подозрительно много jmp... Так ты его меняешь. Ну тогда **backspace**, **backspace**, **alt+230**. Да, мы только что подменили jmp с адреса на запрет доступа, на адрес разрешения доступа.

Было:
```
017D    jmp 0171
```
Стало:
```
017D    jmp 0165
```
![3](https://github.com/ludmilastemp/Crack/assets/138589010/6db48b19-6eec-49d9-92b5-c6958560c3c4)

## Patch

Готово, целых два способа получить желаемое. А если сделать patch... Я буду пробовать это первый раз, но разве это остановит? Это только разогреет интерес!
Си, fopen, fseek, подмена адреса jmp, компиляция... Да! Теперь любой пароль всегда верный. 

Из этого:

![11 (2)](https://github.com/ludmilastemp/Crack/assets/138589010/e9457e9e-bfa4-43a6-981b-1f15e973f504)

Получилось это:

![11 (1)](https://github.com/ludmilastemp/Crack/assets/138589010/2e067dc1-72b4-4fbc-9d34-f64e762e1d38)

Александр, ты думал у тебя получится от меня что-то спрятать? Ха-ха-ха
