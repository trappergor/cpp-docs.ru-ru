---
title: Ошибка средств компоновщика LNK2023
ms.date: 11/04/2016
f1_keywords:
- LNK2023
helpviewer_keywords:
- LNK2023
ms.assetid: c99e35a8-739a-4a20-a715-29b8c3744703
ms.openlocfilehash: c5bc70aeb3a7e39bc60bb745060e7a5740ad7a28
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50658696"
---
# <a name="linker-tools-error-lnk2023"></a>Ошибка средств компоновщика LNK2023

Неверная библиотека dll или точка входа \<dll или точки входа >

Компоновщик загружается неправильная версия библиотеки msobj90.dll. Убедитесь, что link.exe и библиотеки msobj90.dll в пути имеют ту же версию.

Зависимости библиотеки msobj90.dll может отсутствовать. Список зависимостей для библиотеки msobj90.dll является:

- Msvcr90.dll

- Kernel32.dll

Проверьте свой компьютер и другие копии библиотеки msobj90.dll, которые могут быть устаревшими.