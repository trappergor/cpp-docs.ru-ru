---
title: "Включение имен файлов в кавычках | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 789a047e-ea38-4c99-b71d-a2ad9c81daee
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 17c40e74a31341fc3a725c5e5b3823058e403cff
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="including-quoted-filenames"></a>Включение имен файлов в кавычках
**ANSI 3.8.2** Поддержка заключенных в кавычки имен для включаемых файлов исходного кода  
  
 Если указана полная и неоднозначная спецификация пути для включаемого файла между двумя наборами двойных кавычек (" "), препроцессор ищет только спецификацию пути и игнорирует стандартные каталоги.  
  
 Для включаемых файлов, заданных в виде [#include](../preprocessor/hash-include-directive-c-cpp.md) "path-spec", поиск по каталогам начинается с каталога родительского файла и продолжается по каталогам всех прародительских файлов. Таким образом, поиск начинается относительно каталога, который содержит обрабатываемый в настоящее время файл исходного кода. Если отсутствует файл "прародителя" и файл не найден, поиск продолжается, как если бы имя файла было включено в угловые скобки.  
  
## <a name="see-also"></a>См. также  
 [Директивы предварительной обработки](../c-language/preprocessing-directives.md)
