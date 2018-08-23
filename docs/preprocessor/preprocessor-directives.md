---
title: Директивы препроцессора | Документация Майкрософт
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- directives, preprocessor
- preprocessor, directives
ms.assetid: e0fc4564-b6cf-4a36-bf51-6ccd7abd0a94
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc392454a6c5b152411fe8f6a7d0c12457389794
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2018
ms.locfileid: "42541069"
---
# <a name="preprocessor-directives"></a>Директивы препроцессора

Директивы препроцессора, таких как `#define` и `#ifdef`, обычно используются для создания исходные программы с легкостью изменять и компилировать в разных средах выполнения. Директивы в файле исходного кода позволяют препроцессору выполнять определенные действия. Например, препроцессор может заменять токены в тексте, вставлять содержимое других файлов в файл исходного кода или отключать компиляцию части файла путем удаления разделов текста. Строки препроцессора распознаются и выполняются до расширения макросов. Поэтому если макрос разворачивается в нечто, похожее на команду препроцессора, эта команда не распознается препроцессором.

В операторах препроцессора используется тот же набор символов, что и в операторах файла исходного кода, но escape-последовательности не поддерживаются. Набор символов, используемый в операторах препроцессора совпадает со значением [набор символов исполнения](http://msdn.microsoft.com/a7901c61-524d-47c6-beb6-d9dacc2e72ed). Препроцессор также распознает отрицательные значения символов.

Препроцессор распознает следующие директивы:

|||||
|-|-|-|-|
|[#define](../preprocessor/hash-define-directive-c-cpp.md)|[#error](../preprocessor/hash-error-directive-c-cpp.md)|[#import](../preprocessor/hash-import-directive-cpp.md)|[#undef](../preprocessor/hash-undef-directive-c-cpp.md)|
|[#elif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#if](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#include](../preprocessor/hash-include-directive-c-cpp.md)|[#using](../preprocessor/hash-using-directive-cpp.md)|
|[#else](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#ifdef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[#line](../preprocessor/hash-line-directive-c-cpp.md)|[#endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|
|[#ifndef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[#pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)|||

Знак числа (**#**) должен быть первым знаком решетки в строке, содержащей директиву; символы-разделители между могут появиться решетки и первой буквой директивы. Некоторые директивы содержат аргументы или значения. Любой текст, следующий после директивы (за исключением аргумента или значения, который является частью директиву) предваряться разделителем однострочного комментария (**//**) или заключаться в разделители комментариев ( __/ \*\*/__).   Строки, содержащие директивы препроцессора могут ставя непосредственно перед маркер окончания строки, обратной косой чертой (**\\**).

Директивы препроцессора могут находиться в любом месте файла исходного кода, но применяются только к оставшейся части файла.

## <a name="see-also"></a>См. также

[Операторы препроцессора](../preprocessor/preprocessor-operators.md)  
[Предопределенные макросы](../preprocessor/predefined-macros.md)  
[Справочник по препроцессору в C/C++](../preprocessor/c-cpp-preprocessor-reference.md)  
