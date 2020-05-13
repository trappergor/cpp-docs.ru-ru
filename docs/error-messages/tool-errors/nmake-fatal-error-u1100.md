---
title: Неустранимая ошибка NMAKE U1100
ms.date: 11/04/2016
f1_keywords:
- U1100
helpviewer_keywords:
- U1100
ms.assetid: c71910a7-c581-4d9c-a38c-d2d557d56289
ms.openlocfilehash: d5c62c1465bbb6463afbac2bc9ad5f4290473471
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193268"
---
# <a name="nmake-fatal-error-u1100"></a>Неустранимая ошибка NMAKE U1100

недопустимый макрос "имямакроса" в контексте пакетного правила "правило"

NMAKE создает эту ошибку, когда блок команды правила пакетного режима непосредственно или косвенно ссылается на специальный файловый макрос, который не является $ <.

$ < является единственным разрешенным макросом для правил пакетного режима.
