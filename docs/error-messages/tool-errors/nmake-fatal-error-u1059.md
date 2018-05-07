---
title: Неустранимая ошибка NMAKE U1059 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1059
dev_langs:
- C++
helpviewer_keywords:
- U1059
ms.assetid: b21d9198-9c63-40d0-b589-80e17294ce24
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6eb038befdb7c587c6fe2a734003abba585c3e2a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="nmake-fatal-error-u1059"></a>Неустранимая ошибка NMAKE U1059
Синтаксическая ошибка: "}" отсутствует в зависимости  
  
 Неправильно указан путь поиска для зависимости. Существовали пробелы в пути или закрывающей фигурной скобкой (**}**) был пропущен.  
  
 Синтаксис спецификации директории для зависимости:  
  
 **{**   
 ***каталоги* } зависимые**  
  
 где `directories` указывает один или несколько путей, разделяя их точкой с запятой (**;**). Пробелы не допускаются.  
  
 Если макрос заменяется всех или части пути поиска, убедитесь, что в расширении макроса существуют без пробелов.