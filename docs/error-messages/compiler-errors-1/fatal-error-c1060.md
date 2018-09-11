---
title: Неустранимая ошибка C1060 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1060
dev_langs:
- C++
helpviewer_keywords:
- C1060
ms.assetid: feaf305c-c84c-4160-b974-50e283412849
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01b3b25499f46b476d0480ec87b609b36ba8dfd9
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43677708"
---
# <a name="fatal-error-c1060"></a>Неустранимая ошибка C1060
компилятору не хватает размера кучи  
  
 Операционная система или библиотека времени выполнения не могут выполнить запрос на предоставление памяти.  
  
### <a name="to-fix-this-error-try-the-following-possible-solutions"></a>Чтобы устранить эту проблему, попробуйте следующие возможные решения  
  
1.  Если возникают ошибки компилятора [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) и [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md), использовать [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) параметр компилятора, чтобы снизить предел распределения памяти. Если уменьшить распределение оставшейся памяти, в куче останется больше места для вашего приложения.  
  
     Если [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) уже установлен, попробуйте удалить его. Место в куче может быть исчерпано из-за того, что предел распределения памяти, заданный с помощью этого параметра, слишком велик. Компилятор использует ограничение по умолчанию, если удалить [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) параметр.  
  
2.  Если компиляция происходит на 64-разрядной платформе, используйте 64-разрядный набор средств компиляции. Сведения см. в разделе [как: включить 64-разрядных набора инструментов Visual C++ в командной строке](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md).  
  
3.  На 32-разрядной Windows, попробуйте использовать [/3 GB](https://support.microsoft.com/en-us/help/833721/available-switch-options-for-the-windows-xp-and-the-windows-server-200) переключатель в файле boot.ini.  
  
4.  Увеличьте размер файла подкачки Windows.  
  
5.  Закройте все запущенные программы.  
  
6.  Удалите неиспользуемые включенные файлы.  
  
7.  Удалите ненужные глобальные переменные, например, путем динамического распределения памяти вместо объявления крупного массива.  
  
8.  Удалите неиспользуемые объявления.  
  
9. Разделите данный файл на меньшие файлы.