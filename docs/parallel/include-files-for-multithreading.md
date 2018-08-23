---
title: Включаемые файлы для многопоточности | Документация Майкрософт
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
ms.openlocfilehash: 73444c72878073d881abec08c474eb1f1ce64f02
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2018
ms.locfileid: "42541076"
---
# <a name="include-files-for-multithreading"></a>Включаемые файлы для многопоточности
Стандартные включаемые файлы объявления функции библиотеки времени выполнения C, как они реализованы в библиотеках. Если вы используете [Полная оптимизация](../build/reference/ox-full-optimization.md) (/ Ox) или [вызовах fastcall](../build/reference/gd-gr-gv-gz-calling-convention.md) (/ Gr) параметр, компилятор предполагает, что все функции должен вызываться с использованием реестра, соглашение о вызовах. Функции библиотеки времени выполнения, скомпилированные с помощью соглашение о вызовах C, а объявления в стандартных включаемых файлах сообщает компилятору, что для создания правильных внешних ссылок на эти функции.  
  
## <a name="see-also"></a>См. также  

[Реализация многопоточности на языке C с помощью функций Win32](../parallel/multithreading-with-c-and-win32.md)