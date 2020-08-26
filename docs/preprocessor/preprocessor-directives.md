---
title: Директивы препроцессора
ms.date: 08/29/2019
helpviewer_keywords:
- directives, preprocessor
- preprocessor, directives
ms.assetid: e0fc4564-b6cf-4a36-bf51-6ccd7abd0a94
ms.openlocfilehash: ac765d33aec4795e94866c097d6c453dbd0e4a08
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845332"
---
# <a name="preprocessor-directives"></a>Директивы препроцессора

Директивы препроцессора, такие как `#define` и `#ifdef` , обычно используются для упрощения изменения и компиляции исходных программ в разных средах выполнения. Директивы в исходном файле указывают препроцессору на необходимость выполнения определенных действий. Например, препроцессор может заменять токены в тексте, вставлять содержимое других файлов в файл исходного кода или отключать компиляцию части файла путем удаления разделов текста. Строки препроцессора распознаются и выполняются до расширения макросов. Таким образом, если макрос разворачивается в нечто, похожее на команду препроцессора, оно не распознается препроцессором.

Инструкции препроцессора используют тот же набор символов, что и инструкции исходного файла, за исключением того, что escape-последовательности не поддерживаются. Набор символов в операторах препроцессора совпадает с кодировкой выполнения. Препроцессор также распознает отрицательные значения символов.

Препроцессор распознает следующие директивы:

:::row:::
   :::column span="":::
      [`#define`](../preprocessor/hash-define-directive-c-cpp.md)\
      [`#elif`](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)\
      [`#else`](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)\
      [`#endif`](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)
   :::column-end:::
   :::column span="":::
      [`#error`](../preprocessor/hash-error-directive-c-cpp.md)\
      [`#if`](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)\
      [`#ifdef`](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)\
      [`#ifndef`](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)
   :::column-end:::
   :::column span="":::
      [`#import`](../preprocessor/hash-import-directive-cpp.md)\
      [`#include`](../preprocessor/hash-include-directive-c-cpp.md)\
      [`#line`](../preprocessor/hash-line-directive-c-cpp.md)
   :::column-end:::
   :::column span="":::
      [`#pragma`](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
      [`#undef`](../preprocessor/hash-undef-directive-c-cpp.md)\
      [`#using`](../preprocessor/hash-using-directive-cpp.md)
   :::column-end:::
:::row-end:::

Знак решетки ( `#` ) должен быть первым символом, не пробелом, в строке, содержащей директиву. Символы пробела могут находиться между знаком номера и первой буквой директивы. Некоторые директивы содержат аргументы или значения. Любой текст, следующий за директивой (за исключением аргумента или значения, который является частью директивы), должен предшествовать разделителю однострочных комментариев ( `//` ) или заключены в разделители комментариев ( `/* */` ). Строки, содержащие директивы препроцессора, могут быть продолжены непосредственно перед маркером конца строки с обратной косой чертой ( `\` ).

Директивы препроцессора могут находиться в любом месте исходного файла, но они применяются только к остальной части исходного файла после их появления.

## <a name="see-also"></a>См. также раздел

[Операторы препроцессора](../preprocessor/preprocessor-operators.md)\
[Предопределенные макросы](../preprocessor/predefined-macros.md)\
[Справочник по препроцессору c/c++](../preprocessor/c-cpp-preprocessor-reference.md)
