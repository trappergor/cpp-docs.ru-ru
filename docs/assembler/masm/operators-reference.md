---
title: Справочник по операторам MASM
ms.date: 07/15/2020
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), operators reference
- operators [MASM]
ms.assetid: c069cab7-d6b0-4f82-a6ce-0ca3fc7e6428
ms.openlocfilehash: db79473f5d4264b869eeac334fa7957cfe553364
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88830947"
---
# <a name="masm-operators-reference"></a>Справочник по операторам MASM

## <a name="arithmetic"></a>Арифметические

:::row:::
   :::column span="":::
      [`*` перемножаемых](operator-multiply.md)\
      [`+` включить](operator-add.md)\
      [`-` (вычитание или отрицание)](operator-subtract-2.md)
   :::column-end:::
   :::column span="":::
      [`.` полями](operator-dot.md)\
      [`/` деление](operator-subtract-1.md)
   :::column-end:::
   :::column span="":::
      [`[]` номер](operator-brackets.md)\
      [`MOD` дальнейшем](operator-mod.md)
   :::column-end:::
:::row-end:::

## <a name="control-flow"></a>Поток управления

:::row:::
   :::column span="":::
      [`!` (логическое не время выполнения)](operator-logical-not-masm-run-time.md)\
      [`!=` (среда выполнения не равна)](operator-not-equal-masm.md)\
      [`||` (логическая среда выполнения или)](operator-logical-or.md)\
      [`&&` (логическая среда выполнения и)](operator-logical-and-masm-run-time.md)\
      [`<` (среда выполнения меньше)](operator-less-than-masm-run-time.md)
   :::column-end:::
   :::column span="":::
      [`<=` (среда выполнения меньше или равна)](operator-less-or-equal-masm-run-time.md)\
      [`==` (среда выполнения равна)](operator-equal-masm-run-time.md)\
      [`>` (среда выполнения больше)](operator-greater-than-masm-run-time.md)\
      [`>=` (среда выполнения больше или равна)](operator-greater-or-equal-masm-run-time.md)\
      [`&` (Побитовая среда выполнения и)](operator-bitwise-and.md)
   :::column-end:::
   :::column span="":::
      [`CARRY?` (выполнение теста в среде выполнения)](operator-carry-q.md)\
      [`OVERFLOW?` (тест переполнения среды выполнения)](operator-overflow-q.md)\
      [`PARITY?` (проверка четности времени выполнения)](operator-parity-q.md)\
      [`SIGN?` (проверка подписи среды выполнения)](operator-sign-q.md)\
      [`ZERO?` (пустой тест времени выполнения)](operator-zero-q.md)
   :::column-end:::
:::row-end:::

## <a name="logical-and-shift"></a>Логическое и Shift

:::row:::
   :::column span="":::
      [`AND` (побитовое и)](operator-and.md)\
      [`NOT` (побитовое не)](operator-not.md)
   :::column-end:::
   :::column span="":::
      [`OR` (побитовое или)](operator-or.md)\
      [`SHL` (сдвиг влево)](operator-shl.md)
   :::column-end:::
   :::column span="":::
      [`SHR` (сдвиги вправо)](operator-shr.md)\
      [`XOR` (побитовое исключающее или)](operator-xor.md)
   :::column-end:::
:::row-end:::

## <a name="macro"></a>Макрос

:::row:::
   :::column span="":::
      [`!` (символьный литерал)](operator-logical-not-masm.md)\
      [`%` (рассматривать как текст)](operator-percent.md)
   :::column-end:::
   :::column span="":::
      [`;;` (рассматривать как комментарий)](operator-semicolons.md)\
      [`< >` (рассматривать как один литерал)](operator-literal.md)
   :::column-end:::
   :::column span="":::
      [`& &` (замена значения параметра)](operator-logical-and-masm.md)
   :::column-end:::
:::row-end:::

## <a name="miscellaneous"></a>Прочее

:::row:::
   :::column span="":::
      [`' '` (рассматривать как строку)](operator-single-quote.md)\
      [`" "` (рассматривать как строку)](operator-double-quote.md)\
      `:` (определение локальной метки)
   :::column-end:::
   :::column span="":::
      `::` (зарегистрировать сегмент и смещение) \
      `::` (определение глобальной метки)
   :::column-end:::
   :::column span="":::
      [`;` (рассматривать как комментарий)](operator-semicolon.md)\
      [`DUP` (повторное объявление)](operator-dup.md)
   :::column-end:::
:::row-end:::

## <a name="record"></a>Записей

:::row:::
   :::column span="":::
      [`MASK` (получение битовой маски записи или поля)](operator-mask.md)
   :::column-end:::
   :::column span="2":::
      [`WIDTH` (получение ширины записи или поля)](operator-width.md)
   :::column-end:::
:::row-end:::

## <a name="relational"></a>Реляционный

:::row:::
   :::column span="":::
      [`EQ` равномерно](operator-eq.md)\
      [`GE` (больше или равно)](operator-ge.md)
   :::column-end:::
   :::column span="":::
      [`GT` (больше)](operator-gt.md)\
      [`LE` (меньше или равно)](operator-le.md)
   :::column-end:::
   :::column span="":::
      [`LT` (меньше)](operator-lt.md)\
      [`NE` (не равно)](operator-ne.md)
   :::column-end:::
:::row-end:::

## <a name="segment"></a>Segment

:::row:::
   :::column span="":::
      [`:` (переопределение сегмента)](operator-colon.md)\
      `::` (зарегистрировать сегмент и смещение) \
      [`IMAGEREL` (относительное смещение изображения)](operator-imagerel.md)
   :::column-end:::
   :::column span="":::
      [`LROFFSET` (смещение разрешенного загрузчика)](operator-lroffset.md)\
      [`OFFSET` (относительное смещение сегмента)](operator-offset.md)
   :::column-end:::
   :::column span="":::
      [`SECTIONREL` (относительное смещение раздела)](operator-sectionrel.md)\
      [`SEG` (получить сегмент)](operator-seg.md)
   :::column-end:::
:::row-end:::

## <a name="type"></a>Тип

:::row:::
   :::column span="":::
      [`HIGH` (старшие 8 бит с наименьшими 16 битами)](operator-high.md)\
      [`HIGH32` (Старшие 32 бит 64 бит)](operator-high32.md)\
      [`HIGHWORD` (старшие 16 бит от младших 32 бит)](operator-highword.md)\
      [`LENGTH` (число элементов в массиве)](operator-length.md)\
      [`LENGTHOF` (число элементов в массиве)](operator-lengthof.md)\
      [`LOW` (младшие 8 бит)](operator-low.md)
   :::column-end:::
   :::column span="":::
      [`LOW32` (младшие 32 бит)](operator-low32.md)\
      [`LOWWORD` (младшие 16 бит)](operator-lowword.md)\
      [`OPATTR` (получение сведений о типе аргумента)](operator-opattr.md)\
      [`PTR` (указатель на или как тип)](operator-ptr.md)\
      [`SHORT` (пометьте короткий тип метки)](operator-short.md)
   :::column-end:::
   :::column span="":::
      [`SIZE` (размер типа или переменной)](operator-size.md)\
      [`SIZEOF` (размер типа или переменной)](operator-sizeof.md)\
      [`THIS` (текущее расположение)](operator-this.md)\
      [`TYPE` (получение типа выражения)](operator-type.md)\
      [`.TYPE` (получение сведений о типе аргумента)](operator-dot-type.md)
   :::column-end:::
:::row-end:::

## <a name="see-also"></a>См. также раздел

[Справочник по ассемблеру макросов (Майкрософт)](microsoft-macro-assembler-reference.md)\
[Грамматика MASM BNF](masm-bnf-grammar.md)
