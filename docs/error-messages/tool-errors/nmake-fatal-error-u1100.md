---
title: Неустранимая ошибка NMAKE U1100
description: Описание причин неустранимой ошибки Microsoft NMAKE U1100.
ms.date: 07/17/2020
f1_keywords:
- U1100
helpviewer_keywords:
- U1100
ms.assetid: c71910a7-c581-4d9c-a38c-d2d557d56289
ms.openlocfilehash: f908514469a6c9fdb53df3b2bded1b30bddc5a41
ms.sourcegitcommit: 00af3df3331854b23693ee844e5e7c10c8b05a90
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2020
ms.locfileid: "86491392"
---
# <a name="nmake-fatal-error-u1100"></a>Неустранимая ошибка NMAKE U1100

> макрос "*макроопределение-Name*" недопустим в контексте пакетного правила "*rule-name*"

NMAKE создает эту ошибку, когда блок команды правила пакетного режима непосредственно или косвенно ссылается на специальный файловый макрос, который не является `$<` .

`$<`— единственный допустимый макрос для правил пакетного режима.

Дополнительные сведения о макросах NMAKE в пакетных правилах см. в разделе [специальные макросы NMAKE](../../build/reference/special-nmake-macros.md).
