---
title: Включаемые файлы для многопоточности | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- threading [C++], include files
- include files, multithreading
- multithreading [C++], include files
ms.assetid: 98d764f9-71f4-4da5-8f3a-8d2d26e96799
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 62b94f4a7a394b78cb7c6f23275709e4aeacc774
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="include-files-for-multithreading"></a>Включаемые файлы для многопоточности
Стандартные включаемые файлы объявления функции библиотеки времени выполнения C, как они реализованы в библиотеках. Если вы используете [Полная оптимизация](../build/reference/ox-full-optimization.md) (/ Ox) или [вызовах fastcall](../build/reference/gd-gr-gv-gz-calling-convention.md) (/ Gr) параметра, компилятор предполагает, что все функции должны вызываться с использованием соглашения о вызовах реестра. Функции библиотеки времени выполнения были скомпилированы с помощью соглашения о вызовах языка и объявления в стандартных включаемых файлах сообщает компилятору, что для создания правильных внешних ссылок на эти функции.  
  
## <a name="see-also"></a>См. также  
 [Реализация многопоточности на языке C с помощью функций Win32](../parallel/multithreading-with-c-and-win32.md)