---
title: Системные вызовы | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.system
dev_langs:
- C++
helpviewer_keywords:
- Windows [C++], system calls
- system calls
ms.assetid: 0255f2ec-a5a0-487e-8b09-9dad001d81ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 648b0e1addd509652ba67e09d32dbdd060f29e87
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074426"
---
# <a name="system-calls"></a>Системные вызовы

Следующие функции являются вызовами операционной системы Windows.

## <a name="system-call-functions"></a>Функции системных вызовов

|Функция|Использовать|
|--------------|---------|
|[_findclose](../c-runtime-library/reference/findclose.md)|Освобождение ресурсов от предыдущих операций поиска|
|[_findfirst, _findfirst32, _findfirst64, _findfirsti64, _findfirst32i64, _findfirst64i32, _wfindfirst, _wfindfirst32, _wfindfirst64, _wfindfirsti64, _wfindfirst32i64, _wfindfirst64i32](../c-runtime-library/reference/findfirst-functions.md)|Поиск файла с указанными атрибутами|
|[_findnext, _findnext32, _findnext64, _findnexti64, _findnext32i64, _findnext64i32, _wfindnext, _wfindnext32, _wfindnexti64, _wfindnext64, _wfindnexti64](../c-runtime-library/reference/findnext-functions.md)|Поиск следующего файла с указанными атрибутами|

## <a name="see-also"></a>См. также

[Универсальные подпрограммы среды выполнения C по категориям](../c-runtime-library/run-time-routines-by-category.md)<br/>
[Обработка файлов](../c-runtime-library/file-handling.md)<br/>
[Управление каталогами](../c-runtime-library/directory-control.md)<br/>
[Низкоуровневый ввод-вывод](../c-runtime-library/low-level-i-o.md)<br/>
