---
title: Ошибка средств компоновщика LNK2023
ms.date: 11/04/2016
f1_keywords:
- LNK2023
helpviewer_keywords:
- LNK2023
ms.assetid: c99e35a8-739a-4a20-a715-29b8c3744703
ms.openlocfilehash: 363b6ef0ea9991ff5d657044282e99c558257fb9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194633"
---
# <a name="linker-tools-error-lnk2023"></a>Ошибка средств компоновщика LNK2023

Неправильная библиотека DLL или точка входа \<DLL или точка входа >

Компоновщик загружает неправильную версию msobj90. dll. Убедитесь, что файлы Link. exe и msobj90. dll в пути имеют одинаковую версию.

Возможно, отсутствует зависимость от msobj90. dll. Список зависимостей для msobj90. dll:

- Msvcr90. dll

- Kernel32.dll

Проверьте, не устарели ли на вашем компьютере копии msobj90. dll, которые могут устареть.
