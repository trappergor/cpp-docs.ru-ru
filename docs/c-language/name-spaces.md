---
title: Пространства имен
ms.date: 11/04/2016
helpviewer_keywords:
- union keyword [C], tags
- enumeration tags
- structure tags
- names [C++], declared elements
- name spaces [C++]
- tags, structure tags
- union keyword [C]
ms.assetid: b4bda1d1-cb5e-4f60-ac2b-29af93d8a9a2
ms.openlocfilehash: 28036219464e96ae20733473dedb4fab63f6de38
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218823"
---
# <a name="name-spaces"></a>Пространства имен

Компилятор настраивает пространства имен, чтобы различать идентификаторы, используемые для различных типов элементов. Имена в каждом пространстве имен должны быть уникальными во избежание конфликтов, но одинаковые имена могут использоваться в нескольких пространствах имен. Это означает, что можно использовать один и тот же идентификатор для двух или более различных элементов при условии, что элементы расположены в разных пространствах имен. Компилятор может разрешить ссылки на основе синтаксического контекста идентификатора в программе.

> [!NOTE]
> Не следует путать ограниченную нотацию C пространства имен с возможностью пространства имен C++. Дополнительные сведения см. в разделе [Пространства имен (C++)](../cpp/namespaces-cpp.md) в справочнике по языку C++.

Ниже приводится список пространств имен, используемых в C.

Метки операторов. Именованные метки операторов являются частью операторов. За определениями меток операторов всегда следует двоеточие, но определения не являются частью меток **`case`** . Метки операторов всегда используются сразу за ключевым словом **`goto`** . Метки операторов не должны отличаться от других имен или имен меток в других функциях.

Теги структур, объединений и перечислений. Эти теги являются частью указателей на тип структуры, объединения и перечисления и при их наличии всегда следуют сразу за зарезервированными словами **`struct`** , **`union`** или **`enum`** . Имена тегов должны отличаться от всех других тегов структур, перечислений или объединений с такой же видимостью.

Элементы структур или объединений. Имена элементов выделены в пространствах имен, связанных с каждыми типом структуры и объединения. То есть один и тот же идентификатор может быть именем компонента в любом количестве структур или объединений одновременно. Определения имен компонентов всегда находятся в описателях типа структуры или объединения. Имена компонентов всегда следуют сразу за операторами выбора члена ( **->** и **.** ). Имя члена должно быть уникальным в пределах структуры или объединения, но оно не обязательно должно отличаться от других имен в программе, включая имена членов различных структур и объединений или имя самой структуры.

Обычные идентификаторы. Все другие имена находятся в пространстве имен, которое содержит переменные, функции (включая формальные параметры и локальные переменные) и константы перечисления. Имена идентификаторов имеют вложенную видимость, поэтому их можно переопределять в блоках.

Имена typedef. Эти имена нельзя использовать в качестве идентификаторов в одной и той же области.

Например, поскольку теги структуры, члены структуры и имена переменных находятся в трех разных пространствах имен, три элемента с именем `student` в этом примере не конфликтуют. Контекст каждого элемента позволяет правильно интерпретировать каждое вхождение `student` в программе. (Дополнительные сведения о структурах см. в разделе [Объявления структур](../c-language/structure-declarations.md).)

```C
struct student {
   char student[20];
   int class;
   int id;
   } student;
```

Если `student` отображается после ключевого слова **`struct`** , компилятор распознает его как тег структуры. Если `student` отображается после оператора выбора члена ( **->** или **.** ), имя ссылается на член структуры. В других контекстах `student` ссылается на переменную структуры. Однако не рекомендуется перегружать пространство имен тега, поскольку это искажает смысл.

## <a name="see-also"></a>См. также

[Структура программы](../c-language/program-structure.md)
