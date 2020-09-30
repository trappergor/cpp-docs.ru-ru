---
title: Инициализация CRT
description: Описывает, как CRT инициализирует глобальное состояние в машинном коде.
ms.topic: conceptual
ms.date: 11/04/2016
helpviewer_keywords:
- CRT initialization [C++]
ms.assetid: e7979813-1856-4848-9639-f29c86b74ad7
ms.openlocfilehash: 25f1e2a7e5b7d91c729bb45bd79ba9a8720cead1
ms.sourcegitcommit: 9451db8480992017c46f9d2df23fb17b503bbe74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2020
ms.locfileid: "91589774"
---
# <a name="crt-initialization"></a>Инициализация CRT

В этом разделе описывается, как CRT инициализирует глобальное состояние в машинном коде.

По умолчанию компоновщик включает библиотеку CRT, которая предоставляет собственный код запуска. Этот код запуска инициализирует библиотеку CRT, вызывает глобальные инициализаторы и затем вызывает предоставленную пользователем функцию `main` для консольных приложений.

## <a name="initializing-a-global-object"></a>Инициализация глобального объекта

Рассмотрим следующий код.

```
int func(void)
{
    return 3;
}

int gi = func();

int main()
{
    return gi;
}
```

В соответствии со стандартом C/C++, функцию `func()` необходимо вызывать перед выполнением функции `main()`. Однако кто ее вызывает?

Одним из способов определения вызывающего объекта является установка точки останова в `func()` , отладке приложения и изучение стека. Это возможно, поскольку исходный код CRT входит в состав Visual Studio.

При просмотре функций в стеке вы увидите, что CRT вызывает список указателей на функции. Эти функции похожи на `func()` , или конструкторы для экземпляров класса.

CRT получает список указателей функций из компилятора Microsoft C++. Когда компилятор видит глобальный инициализатор, он создает динамический инициализатор в `.CRT$XCU` разделе, где `CRT` — это имя раздела, а `XCU` — имя группы. Чтобы получить список динамических инициализаторов, выполните команду **dumpbin/ALL Main. obj**, а затем выполните поиск в `.CRT$XCU` разделе. Это относится к компиляции Main. cpp в виде файла C++, а не файла C. Он будет похож на следующий пример:

```
SECTION HEADER #6
.CRT$XCU name
       0 physical address
       0 virtual address
       4 size of raw data
     1F2 file pointer to raw data (000001F2 to 000001F5)
     1F6 file pointer to relocation table
       0 file pointer to line numbers
       1 number of relocations
       0 number of line numbers
40300040 flags
         Initialized Data
         4 byte align
         Read Only

RAW DATA #6
  00000000: 00 00 00 00                                      ....

RELOCATIONS #6
                                               Symbol    Symbol
Offset    Type              Applied To         Index     Name
--------  ----------------  -----------------  --------  -------
00000000  DIR32             00000000           C         ??__Egi@@YAXXZ (void __cdecl `dynamic initializer for 'gi''(void))
```

CRT определяет два указателя:

- `__xc_a` в `.CRT$XCA`

- `__xc_z` в `.CRT$XCZ`

Ни одна из групп не имеет определенных символов `__xc_a` , кроме и `__xc_z` .

Теперь, когда компоновщик считывает различные группы `.CRT`, он объединяет их в одном разделе и упорядочивает их по алфавиту. Это означает, что определяемые пользователем глобальные инициализаторы (которые компилятор Microsoft C++ помещает в `.CRT$XCU`) всегда будут идти после `.CRT$XCA` и перед `.CRT$XCZ`.

Раздел будет выглядеть следующим образом:

```
.CRT$XCA
            __xc_a
.CRT$XCU
            Pointer to Global Initializer 1
            Pointer to Global Initializer 2
.CRT$XCZ
            __xc_z
```

Таким образом, Библиотека CRT использует `__xc_a` и `__xc_z` для определения начала и конца списка глобальных инициализаторов из-за способа их расположения в памяти после загрузки изображения.

## <a name="see-also"></a>См. также

[Возможности библиотеки CRT](../c-runtime-library/crt-library-features.md)
