---
title: "Включаемые файлы для многопоточности | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- threading [C++], include files
- include files, multithreading
- multithreading [C++], include files
ms.assetid: 98d764f9-71f4-4da5-8f3a-8d2d26e96799
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0f71b52bca5f636d80f2d55cc5e9ffc3e217d90a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="include-files-for-multithreading"></a>Включаемые файлы для многопоточности
Стандартные включаемые файлы объявления функции библиотеки времени выполнения C, как они реализованы в библиотеках. Если вы используете [Полная оптимизация](../build/reference/ox-full-optimization.md) (/ Ox) или [вызовах fastcall](../build/reference/gd-gr-gv-gz-calling-convention.md) (/ Gr) параметра, компилятор предполагает, что все функции должны вызываться с использованием соглашения о вызовах реестра. Функции библиотеки времени выполнения были скомпилированы с помощью соглашения о вызовах языка и объявления в стандартных включаемых файлах сообщает компилятору, что для создания правильных внешних ссылок на эти функции.  
  
## <a name="see-also"></a>См. также  
 [Реализация многопоточности на языке C с помощью функций Win32](../parallel/multithreading-with-c-and-win32.md)