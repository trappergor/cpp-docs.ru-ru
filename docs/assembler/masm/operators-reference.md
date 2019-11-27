---
title: Справочник по операторам MASM
ms.date: 08/30/2018
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), operators reference
- operators [MASM]
ms.assetid: c069cab7-d6b0-4f82-a6ce-0ca3fc7e6428
ms.openlocfilehash: 5295307ad668b76e5ff39882ce2613f2042f914a
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74395212"
---
# <a name="masm-operators-reference"></a>Справочник по операторам MASM

## <a name="arithmetic"></a>Вычисления

||||
|-|-|-|
|[* (умножение)](operator-multiply.md)|[+ (Добавить)](operator-add.md)|[-(вычитание или отрицание)](operator-subtract-2.md)|
|[. полями](operator-dot.md)|[/(деление)](operator-subtract-1.md)|[&#91;&#93;номер](operator-brackets.md)|
|[MOD (остаток)](operator-mod.md)|||

## <a name="control-flow"></a>Поток управления

||||
|-|-|-|
|[\! (логическое не время выполнения)](operator-logical-not-masm-run-time.md)|[\!= (среда выполнения не равна)](operator-not-equal-masm.md)|[&#124;&#124;(логическая среда выполнения или)](operator-logical-or.md)|
|[& & (логическое и в среде выполнения)](operator-logical-and-masm-run-time.md)|[< (среда выполнения меньше)](operator-less-than-masm-run-time.md)|[\<= (время выполнения меньше или равно)](operator-less-or-equal-masm-run-time.md)|
|[= = (среда выполнения равна)](operator-equal-masm-run-time.md)|[> (среда выполнения больше)](operator-greater-than-masm-run-time.md)|[> = (время выполнения больше или равно)](operator-greater-or-equal-masm-run-time.md)|
|[& (побитовое и)](operator-bitwise-and.md)|||
|[СОХРАНЯЯ? (выполнение теста в среде выполнения)](operator-carry-q.md)|[ПОЛН? (тест переполнения среды выполнения)](operator-overflow-q.md)|[СУММЫ? (проверка четности времени выполнения)](operator-parity-q.md)|
|[ПИСАТЬ? (проверка подписи среды выполнения)](operator-sign-q.md)|[НУЛЬ? (пустой тест времени выполнения)](operator-zero-q.md)||

## <a name="logical-and-shift"></a>Логическое и Shift

||||
|-|-|-|
|[И (побитовое и)](operator-and.md)|[НЕ (побитовое не)](operator-not.md)|[ИЛИ (побитовое или)](operator-or.md)|
|[Шл (сдвиг влево)](operator-shl.md)|[SHR (сдвигы вправо)](operator-shr.md)|[XOR (побитовое исключающее или)](operator-xor.md)|

## <a name="macro"></a>Макрос

||||
|-|-|-|
|[\! (символьный литерал)](operator-logical-not-masm.md)|[% (рассматривать как текст)](operator-percent.md)||
|[;; (рассматривать как комментарий)](operator-semicolons.md)|[&lt; &gt; (обрабатываются как один литерал)](operator-literal.md)|[& & (значение параметра заменяется)](operator-logical-and-masm.md)|

## <a name="miscellaneous"></a>Прочее

||||
|-|-|-|
|["" (обрабатывается как строка)](operator-single-quote.md)|["" (рассматривать как строку)](operator-double-quote.md)||
|: (определение локальной метки)|:: (зарегистрировать сегмент и смещение)|:: (определение глобальной метки)|
|[; (рассматривать как комментарий)](operator-semicolon.md)|[DUP (повторное объявление)](operator-dup.md)||

## <a name="record"></a>Запись

|||
|-|-|
|[MASK (получение битовой маски записи или поля)](operator-mask.md)|[Ширина (получение записи или ширина поля)](operator-width.md)|

## <a name="relational"></a>Реляционный

||||
|-|-|-|
|[EQ (равно)](operator-eq.md)|[GE (больше или равно)](operator-ge.md)|[GT (больше)](operator-gt.md)|
|[LE (меньше или равно)](operator-le.md)|[LT (меньше)](operator-lt.md)|[NE (не равно)](operator-ne.md)|

## <a name="segment"></a>Сегментаци

|||
|-|-|
|[: (переопределение сегмента)](operator-colon.md)|:: (зарегистрировать сегмент и смещение)|
|[IMAGEREL (относительное смещение изображения)](operator-imagerel.md)|[ЛРОФФСЕТ (смещение, разрешенное загрузчиком)](operator-lroffset.md)|
|[OFFSET (относительное смещение сегмента)](operator-offset.md)|[SECTIONREL (относительное смещение раздела)](operator-sectionrel.md)|
|[SEG (получение сегмента)](operator-seg.md)||

## <a name="type"></a>Тип

||||
|-|-|-|
|[ВЫСОКИЙ (старшие 8 бит с наименьшим 16 битами)](operator-high.md)|[HIGH32 (Старшие 32 бит 64 бит)](operator-high32.md)|[HIGHWORD (старшие 16 бит от младших 32 бит)](operator-highword.md)|
|[Длина (число элементов в массиве)](operator-length.md)|[LENGTHOF (число элементов в массиве)](operator-lengthof.md)|[НИЗКИЙ (младшие 8 бит)](operator-low.md)|
|[LOW32 (младшие 32 бита)](operator-low32.md)|[LOWWORD (младшие 16 бит)](operator-lowword.md)|[OPATTR (получение сведений о типе аргумента)](operator-opattr.md)|
|[PTR (указатель на или как тип)](operator-ptr.md)|[КОРОТКИЙ (отметить короткий тип метки)](operator-short.md)|[Размер (размер типа или переменной)](operator-size.md)|
|[SIZEOF (размер типа или переменной)](operator-sizeof.md)|[Это (текущее расположение)](operator-this.md)|[ТИП (получение типа выражения)](operator-type.md)|
|[. ТИП (получение сведений о типе аргумента)](operator-dot-type.md)|||

## <a name="see-also"></a>См. также:

[Справочные материалы по ассемблеру Microsoft Macro Assembler](microsoft-macro-assembler-reference.md)<br/>
