---
title: Неустранимая ошибка NMAKE U1087
ms.date: 11/04/2016
f1_keywords:
- U1087
helpviewer_keywords:
- U1087
ms.assetid: 5236ab54-e117-484d-99c3-852b061fd3d0
ms.openlocfilehash: ad6f422f42b2ba284a2886065b6181b879e7c7fc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193516"
---
# <a name="nmake-fatal-error-u1087"></a>Неустранимая ошибка NMAKE U1087

не может иметь: и:: зависимые объекты для одного и того же целевого объекта

Целевой объект не может быть указан одновременно как с одиночным двоеточием ( **:** ), так и с помощью зависимости с двойным двоеточием (`::`).

Чтобы указать целевой объект в нескольких блоках описания, используйте `::` в каждой строке зависимости.
