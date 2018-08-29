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
ms.openlocfilehash: ec531c2c0eeac14a617a3e0e3b450cf467808165
ms.sourcegitcommit: f7703076b850c717c33d72fb0755fbb2215c5ddc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2018
ms.locfileid: "43130772"
---
# <a name="include-files-for-multithreading"></a>Включаемые файлы для многопоточности
Стандартные включаемые файлы объявления функции библиотеки времени выполнения C, как они реализованы в библиотеках. Если вы используете [Полная оптимизация](../build/reference/ox-full-optimization.md) (/ Ox) или [вызовах fastcall](../build/reference/gd-gr-gv-gz-calling-convention.md) (/ Gr) параметр, компилятор предполагает, что все функции должен вызываться с использованием реестра, соглашение о вызовах. Функции библиотеки времени выполнения, скомпилированные с помощью соглашение о вызовах C, а объявления в стандартных включаемых файлах сообщает компилятору, что для создания правильных внешних ссылок на эти функции.  
  
## <a name="see-also"></a>См. также  

[Реализация многопоточности на языке C с помощью функций Win32](multithreading-with-c-and-win32.md)