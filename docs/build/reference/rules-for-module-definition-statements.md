---
title: Правила для операторов определения модуля
ms.date: 11/04/2016
f1_keywords:
- .def
helpviewer_keywords:
- module definition files, statement syntax
- module definition files
ms.assetid: f65cd3a7-65d7-4d06-939f-a8b1ecd50f2d
ms.openlocfilehash: f6269ad2d5bf3952e485f2ca5e5d1f411c5f1e0c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62318515"
---
# <a name="rules-for-module-definition-statements"></a>Правила для операторов определения модуля

Применяются следующие правила синтаксиса для всех инструкций в DEF-файл. Другие правила, которые относятся к конкретному оператору, описаны в каждой инструкции.

- Инструкции, ключевые слова атрибута и определяемое пользователем идентификаторы чувствительны к регистру.

- Длинные имена файлов, содержащие пробелы или точки с запятой (;) должен быть заключен в кавычки («).

- Чтобы отделить ключевое слово оператора из его аргументов и для разделения инструкций друг от друга, используйте один или несколько пробелов, табуляции и символы новой строки. Двоеточие (:) или знак равенства (=), указывающий аргумент заключается в ноль или дополнительные пробелы, табуляции и символы новой строки.

- Объект **имя** или **БИБЛИОТЕКИ** инструкции, если используется, должны предшествовать всем другим операторам.

- **РАЗДЕЛАХ** и **ЭКСПОРТОВ** операторы могут использоваться более одного раза в DEF-файле. Каждый оператор может иметь несколько спецификаций, которые должны быть разделены один или несколько пробелов, табуляции и символы новой строки. Ключевое слово оператора должен использоваться один раз перед первой спецификации и может повторяться перед каждой дополнительной спецификацией.

- Многие операторы имеют аналогичный параметр командной строки ссылки. См. в описании соответствующего параметра ССЫЛКУ для получения дополнительных сведений.

- Комментарии в DEF-файле обозначаются точку с запятой (;) в начале каждой строки комментария. Комментарий не могут совместно использовать строку с оператором, но он может находиться в многострочной инструкции. (**РАЗДЕЛАХ** и **ЭКСПОРТОВ** многострочной инструкции.)

- Числовые аргументы указываются в десятеричной или шестнадцатеричное.

- Если строковый аргумент соответствует [зарезервированное слово](reserved-words.md), он должен быть заключен в двойные кавычки ("«).

## <a name="see-also"></a>См. также

[Файлы определения модуля (DEF)](module-definition-dot-def-files.md)
