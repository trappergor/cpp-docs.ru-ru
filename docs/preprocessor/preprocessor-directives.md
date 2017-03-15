---
title: "Директивы препроцессора | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "директивы, препроцессор"
  - "препроцессор, директивы"
ms.assetid: e0fc4564-b6cf-4a36-bf51-6ccd7abd0a94
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Директивы препроцессора
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Директивы препроцессора, такие как `#define` и **\#ifdef**, обычно используются для того, чтобы облегчить изменение исходного кода программ и их компиляцию в разных средах выполнения.  Директивы в файле исходного кода позволяют препроцессору выполнять определенные действия.  Например, препроцессор может заменять токены в тексте, вставлять содержимое других файлов в файл исходного кода или отключать компиляцию части файла путем удаления разделов текста.  Строки препроцессора распознаются и выполняются до расширения макросов.  Поэтому если макрос разворачивается в нечто, похожее на команду препроцессора, эта команда не распознается препроцессором.  
  
 В операторах препроцессора используется тот же набор символов, что и в операторах файла исходного кода, но escape\-последовательности не поддерживаются.  Набор символов в операторах препроцессора совпадает с [кодировкой выполнения](http://msdn.microsoft.com/ru-ru/a7901c61-524d-47c6-beb6-d9dacc2e72ed).  Препроцессор также распознает отрицательные значения символов.  
  
 Препроцессор распознает следующие директивы:  
  
|||||  
|-|-|-|-|  
|[\#define](../preprocessor/hash-define-directive-c-cpp.md)|[\#error](../preprocessor/hash-error-directive-c-cpp.md)|[\#import](../Topic/%23import%20Directive%20\(C++\).md)|[\#undef](../preprocessor/hash-undef-directive-c-cpp.md)|  
|[\#elif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[\#if](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[\#include](../preprocessor/hash-include-directive-c-cpp.md)|[\#using](../preprocessor/hash-using-directive-cpp.md)|  
|[\#else](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[\#ifdef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[\#line](../Topic/%23line%20Directive%20\(C-C++\).md)|[\#endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|  
|[\#ifndef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[\#pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)|||  
  
 Знак решетки \(**\#**\) должен быть первым непробельным символом в строке, содержащей директиву; между знаком решетки и первой буквой директивы пробельные символы допускаются.  Некоторые директивы содержат аргументы или значения.  Любой текст, следующий после директивы \(за исключением аргумента или значения, представляющих собой часть директивы\), должен предваряться разделителем однострочного комментария \(**\/\/**\) или заключаться в разделители комментариев \(**\/\* \*\/**\).  Строки, содержащие директивы препроцессора, можно продолжать, ставя непосредственно перед маркером конца строки обратную косую черту \(**\\**\).  
  
 Директивы препроцессора могут находиться в любом месте файла исходного кода, но применяются только к оставшейся части файла.  
  
## См. также  
 [Операторы препроцессора](../preprocessor/preprocessor-operators.md)   
 [Предустановленный макрос](../preprocessor/predefined-macros.md)   
 [Справочник по препроцессору C\/C\+\+](../preprocessor/c-cpp-preprocessor-reference.md)