---
title: Справочник по операторам MASM
ms.date: 07/15/2020
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), operators reference
- operators [MASM]
ms.assetid: c069cab7-d6b0-4f82-a6ce-0ca3fc7e6428
ms.openlocfilehash: c29b173a1dcf29c297e41f136044599fbd5218a5
ms.sourcegitcommit: e15b46ea7888dbdd7e0bb47da76aeed680c3c1f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/17/2020
ms.locfileid: "86446467"
---
# <a name="masm-operators-reference"></a>Справочник по операторам MASM

## <a name="arithmetic"></a>Арифметические

:::row:::
   :::column span="":::
      [`*`перемножаемых](operator-multiply.md)<br/>[`+`включить](operator-add.md)<br/>[`-`(вычитание или отрицание)](operator-subtract-2.md)
   :::column-end:::
   :::column span="":::
      [`.`полями](operator-dot.md)<br/>[`/`деление](operator-subtract-1.md)
   :::column-end:::
   :::column span="":::
      [`[]`номер](operator-brackets.md)<br/>[`MOD`дальнейшем](operator-mod.md)
   :::column-end:::
:::row-end:::

## <a name="control-flow"></a>Поток управления

:::row:::
   :::column span="":::
      [`!`(логическое не время выполнения)](operator-logical-not-masm-run-time.md)<br/>[`!=`(среда выполнения не равна)](operator-not-equal-masm.md)<br/>[`||`(логическая среда выполнения или)](operator-logical-or.md)<br/>[`&&`(логическая среда выполнения и)](operator-logical-and-masm-run-time.md)<br/>[`<`(среда выполнения меньше)](operator-less-than-masm-run-time.md)
   :::column-end:::
   :::column span="":::
      [`<=`(среда выполнения меньше или равна)](operator-less-or-equal-masm-run-time.md)<br/>[`==`(среда выполнения равна)](operator-equal-masm-run-time.md)<br/>[`>`(среда выполнения больше)](operator-greater-than-masm-run-time.md)<br/>[`>=`(среда выполнения больше или равна)](operator-greater-or-equal-masm-run-time.md)<br/>[`&`(Побитовая среда выполнения и)](operator-bitwise-and.md)
   :::column-end:::
   :::column span="":::
      [`CARRY?`(выполнение теста в среде выполнения)](operator-carry-q.md)<br/>[`OVERFLOW?`(тест переполнения среды выполнения)](operator-overflow-q.md)<br/>[`PARITY?`(проверка четности времени выполнения)](operator-parity-q.md)<br/>[`SIGN?`(проверка подписи среды выполнения)](operator-sign-q.md)<br/>[`ZERO?`(пустой тест времени выполнения)](operator-zero-q.md)
   :::column-end:::
:::row-end:::

## <a name="logical-and-shift"></a>Логическое и Shift

:::row:::
   :::column span="":::
      [`AND`(побитовое и)](operator-and.md)<br/>[`NOT`(побитовое не)](operator-not.md)
   :::column-end:::
   :::column span="":::
      [`OR`(побитовое или)](operator-or.md)<br/>[`SHL`(сдвиг влево)](operator-shl.md)
   :::column-end:::
   :::column span="":::
      [`SHR`(сдвиги вправо)](operator-shr.md)<br/>[`XOR`(побитовое исключающее или)](operator-xor.md)
   :::column-end:::
:::row-end:::

## <a name="macro"></a>Макрос

:::row:::
   :::column span="":::
      [`!`(символьный литерал)](operator-logical-not-masm.md)<br/>[`%`(рассматривать как текст)](operator-percent.md)
   :::column-end:::
   :::column span="":::
      [`;;`(рассматривать как комментарий)](operator-semicolons.md)<br/>[`< >`(рассматривать как один литерал)](operator-literal.md)
   :::column-end:::
   :::column span="":::
      [`& &`(замена значения параметра)](operator-logical-and-masm.md)
   :::column-end:::
:::row-end:::

## <a name="miscellaneous"></a>Прочее

:::row:::
   :::column span="":::
      [`' '`(рассматривать как строку)](operator-single-quote.md)<br/>[`" "`(рассматривать как строку)](operator-double-quote.md)<br/>`:`(определение локальной метки)
   :::column-end:::
   :::column span="":::
      `::`(зарегистрировать сегмент и смещение)<br/>`::`(определение глобальной метки)
   :::column-end:::
   :::column span="":::
      [`;`(рассматривать как комментарий)](operator-semicolon.md)<br/>[`DUP`(повторное объявление)](operator-dup.md)
   :::column-end:::
:::row-end:::

## <a name="record"></a>Запись

:::row:::
   :::column span="":::
      [`MASK`(получение битовой маски записи или поля)](operator-mask.md)
   :::column-end:::
   :::column span="2":::
      [`WIDTH`(получение ширины записи или поля)](operator-width.md)
   :::column-end:::
:::row-end:::

## <a name="relational"></a>Отношение

:::row:::
   :::column span="":::
      [`EQ`равномерно](operator-eq.md)<br/>[`GE`(больше или равно)](operator-ge.md)
   :::column-end:::
   :::column span="":::
      [`GT`(больше)](operator-gt.md)<br/>[`LE`(меньше или равно)](operator-le.md)
   :::column-end:::
   :::column span="":::
      [`LT`(меньше)](operator-lt.md)<br/>[`NE`(не равно)](operator-ne.md)
   :::column-end:::
:::row-end:::

## <a name="segment"></a>Segment

:::row:::
   :::column span="":::
      [`:`(переопределение сегмента)](operator-colon.md)<br/>`::`(зарегистрировать сегмент и смещение)<br/>[`IMAGEREL`(относительное смещение изображения)](operator-imagerel.md)
   :::column-end:::
   :::column span="":::
      [`LROFFSET`(смещение разрешенного загрузчика)](operator-lroffset.md)<br/>[`OFFSET`(относительное смещение сегмента)](operator-offset.md)
   :::column-end:::
   :::column span="":::
      [`SECTIONREL`(относительное смещение раздела)](operator-sectionrel.md)<br/>[`SEG`(получить сегмент)](operator-seg.md)
   :::column-end:::
:::row-end:::

## <a name="type"></a>Тип

:::row:::
   :::column span="":::
      [`HIGH`(старшие 8 бит с наименьшими 16 битами)](operator-high.md)<br/>[`HIGH32`(Старшие 32 бит 64 бит)](operator-high32.md)<br/>[`HIGHWORD`(старшие 16 бит от младших 32 бит)](operator-highword.md)<br/>[`LENGTH`(число элементов в массиве)](operator-length.md)<br/>[`LENGTHOF`(число элементов в массиве)](operator-lengthof.md)<br/>[`LOW`(младшие 8 бит)](operator-low.md)
   :::column-end:::
   :::column span="":::
      [`LOW32`(младшие 32 бит)](operator-low32.md)<br/>[`LOWWORD`(младшие 16 бит)](operator-lowword.md)<br/>[`OPATTR`(получение сведений о типе аргумента)](operator-opattr.md)<br/>[`PTR`(указатель на или как тип)](operator-ptr.md)<br/>[`SHORT`(пометьте короткий тип метки)](operator-short.md)
   :::column-end:::
   :::column span="":::
      [`SIZE`(размер типа или переменной)](operator-size.md)<br/>[`SIZEOF`(размер типа или переменной)](operator-sizeof.md)<br/>[`THIS`(текущее расположение)](operator-this.md)<br/>[`TYPE`(получение типа выражения)](operator-type.md)<br/>[`.TYPE`(получение сведений о типе аргумента)](operator-dot-type.md)
   :::column-end:::
:::row-end:::

## <a name="see-also"></a>Дополнительно

[Справочник по ассемблеру макросов (Майкрософт)](microsoft-macro-assembler-reference.md)\
[Грамматика MASM BNF](masm-bnf-grammar.md)
