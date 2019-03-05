---
title: Включаемые файлы для многопоточности
ms.date: 11/04/2016
helpviewer_keywords:
- threading [C++], include files
- include files, multithreading
- multithreading [C++], include files
ms.assetid: 98d764f9-71f4-4da5-8f3a-8d2d26e96799
ms.openlocfilehash: 79b5c56eecfaf28743eec4ba6b4cee56156d6e2c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57257428"
---
# <a name="include-files-for-multithreading"></a>Включаемые файлы для многопоточности

Стандартные включаемые файлы объявления функции библиотеки времени выполнения C, как они реализованы в библиотеках. Если вы используете [Полная оптимизация](../build/reference/ox-full-optimization.md) (/ Ox) или [вызовах fastcall](../build/reference/gd-gr-gv-gz-calling-convention.md) (/ Gr) параметр, компилятор предполагает, что все функции должен вызываться с использованием реестра, соглашение о вызовах. Функции библиотеки времени выполнения, скомпилированные с помощью соглашение о вызовах C, а объявления в стандартных включаемых файлах сообщает компилятору, что для создания правильных внешних ссылок на эти функции.

## <a name="see-also"></a>См. также

[Реализация многопоточности на языке C с помощью функций Win32](multithreading-with-c-and-win32.md)
