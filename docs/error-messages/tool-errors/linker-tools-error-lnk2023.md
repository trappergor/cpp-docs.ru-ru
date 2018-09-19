---
title: Ошибка средств компоновщика LNK2023 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2023
dev_langs:
- C++
helpviewer_keywords:
- LNK2023
ms.assetid: c99e35a8-739a-4a20-a715-29b8c3744703
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7d8deaf8bfb10d3ceb56380560320ebb2cf9a7b8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090325"
---
# <a name="linker-tools-error-lnk2023"></a>Ошибка средств компоновщика LNK2023

Неверная библиотека dll или точка входа \<dll или точки входа >

Компоновщик загружается неправильная версия библиотеки msobj90.dll. Убедитесь, что link.exe и библиотеки msobj90.dll в пути имеют ту же версию.

Зависимости библиотеки msobj90.dll может отсутствовать. Список зависимостей для библиотеки msobj90.dll является:

- Msvcr90.dll

- Kernel32.dll

Проверьте свой компьютер и другие копии библиотеки msobj90.dll, которые могут быть устаревшими.