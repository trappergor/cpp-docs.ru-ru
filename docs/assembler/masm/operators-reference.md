---
title: Справочник по операторам MASM | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), operators reference
- operators [MASM]
ms.assetid: c069cab7-d6b0-4f82-a6ce-0ca3fc7e6428
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e4708af3c0fa272a1ca803f549ce8953caccaa27
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43688180"
---
# <a name="masm-operators-reference"></a>Справочник по операторам MASM

## <a name="arithmetic"></a>арифметические операции

||||
|-|-|-|
|[* (умножение)](operator-multiply.md)|[+ (сложение)](operator-add.md)|[-(вычитание или Инвертировать)](operator-subtract-2.md)|
|[. (поле)](operator-dot.md)|[/ (деление)](operator-subtract-1.md)|[&#91;&#93;(индекс)](operator-brackets.md)|
|[MOD (остаток от деления)](operator-mod.md)|||

## <a name="control-flow"></a>Управление ходом выполнения

||||
|-|-|-|
|[! (логическое не среды выполнения)](operator-logical-not-masm-run-time.md)|[! = (среда выполнения не равно)](operator-not-equal-masm.md)|[&#124;&#124;(среда выполнения логического или)](operator-logical-or.md)|
|[& & (среда выполнения логического и)](operator-logical-and-masm-run-time.md)|[< (среда выполнения меньше, чем)](operator-less-than-masm-run-time.md)|[\<= (среда выполнения, меньше или равно)](operator-less-or-equal-masm-run-time.md)|
|[== (равно среда выполнения)](operator-equal-masm-run-time.md)|[> (больше, чем среда выполнения)](operator-greater-than-masm-run-time.md)|[> = (среда выполнения больше или равно)](operator-greater-or-equal-masm-run-time.md)|
|[& (среда выполнения побитовое и)](operator-bitwise-and.md)|||
|[CARRY? (тестирование переносом среды выполнения)](operator-carry-q.md)|[OVERFLOW? (проверка переполнения среды выполнения)](operator-overflow-q.md)|[ЧЕТНОСТЬ? (проверка четности среды выполнения)](operator-parity-q.md)|
|[РЕГИСТРАЦИЯ? (среда выполнения знаковый тест)](operator-sign-q.md)|[НОЛЬ? (тестирование нулю среда выполнения)](operator-zero-q.md)||

## <a name="logical-and-shift"></a>Логическое and -Shift

||||
|-|-|-|
|[И (побитовое и)](operator-and.md)|[НЕ (побитовое не)](operator-not.md)|[OR (побитовое или)](operator-or.md)|
|[SHL (сдвига битов влево)](operator-shl.md)|[SHR (shift бит справа)](operator-shr.md)|[XOR (побитовое исключающее или)](operator-xor.md)|

## <a name="macro"></a>Макрос

||||
|-|-|-|
|[! (символьного литерала)](operator-logical-not-masm.md)|[% (Power BI как текст)](operator-percent.md)||
|[;; (следует считать комментария)](operator-semicolons.md)|[&lt; &gt; (следует считать один литерал)](operator-literal.md)|[& & (замените значение параметра)](operator-logical-and-masm.md)|

## <a name="miscellaneous"></a>Прочее

||||
|-|-|-|
|["" (обрабатывать как строка)](operator-single-quote.md)|["" (обрабатывать как строка)](operator-double-quote.md)||
|: (локальный метки определение)|:: (регистрация сегмента и смещения)|:: (глобальные метки определение)|
|[; (следует считать комментария)](operator-semicolon.md)|[DUP (повторите объявление)](operator-dup.md)||

## <a name="record"></a>Запись

|||
|-|-|
|[Маска (получить битовой маски записи или поля)](operator-mask.md)|[Ширина (получить ширины поля или записи)](operator-width.md)|

## <a name="relational"></a>Реляционный

||||
|-|-|-|
|[EQ (равно)](operator-eq.md)|[GE (больше или равно)](operator-ge.md)|[GT (больше)](operator-gt.md)|
|[LE (меньше или равно)](operator-le.md)|[LT (меньше)](operator-lt.md)|[NE (не равно)](operator-ne.md)|

## <a name="segment"></a>Сегмент

|||
|-|-|
|[: (сегмент переопределения)](operator-colon.md)|:: (регистрация сегмента и смещения)|
|[IMAGEREL (относительное смещение изображения)](operator-imagerel.md)|[LROFFSET (загрузчик устранения смещения)](operator-lroffset.md)|
|[СМЕЩЕНИЕ (относительное смещение сегмента)](operator-offset.md)|[SECTIONREL (относительное смещение раздела)](operator-sectionrel.md)|
|[SEG (сегмент get)](operator-seg.md)||

## <a name="type"></a>Тип

||||
|-|-|-|
|[HIGH (высокий уровень 8 бит младшие 16 битов)](operator-high.md)|[HIGH32 (старшие 32 разряда 64 бита)](operator-high32.md)|[HIGHWORD (старшие 16 разрядов наименьшее 32 бита)](operator-highword.md)|
|[Длина (число элементов в массиве)](operator-length.md)|[LENGTHOF (количество элементов в массиве)](operator-lengthof.md)|[LOW (низкий 8 бит)](operator-low.md)|
|[LOW32 (младшие 32 бита)](operator-low32.md)|[LOWWORD (младшие 16 разрядов)](operator-lowword.md)|[OPATTR (информация о типе аргумента get)](operator-opattr.md)|
|[PTR (указатель или тип)](operator-ptr.md)|[КОРОТКОЕ (короткий метка типов)](operator-short.md)|[РАЗМЕР (размер типа или переменной)](operator-size.md)|
|[SIZEOF (размер типа или переменной)](operator-sizeof.md)|[Это (местоположение)](operator-this.md)|[Get выражение (тип)](operator-type.md)|
|[. ТИП (информация о типе аргумента get)](operator-dot-type.md)|||

## <a name="see-also"></a>См. также

[Справочные материалы по ассемблеру Microsoft Macro Assembler](microsoft-macro-assembler-reference.md)<br/>