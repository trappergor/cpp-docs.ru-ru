---
title: Ошибка BSCMAKE BK1506 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK1506
dev_langs:
- C++
helpviewer_keywords:
- BK1506
ms.assetid: f51f8cea-f8fc-4323-bcf2-b7bd119792ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 26201a894212701cca19ab2192676b37a69e8b57
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088700"
---
# <a name="bscmake-error-bk1506"></a>Ошибка BSCMAKE BK1506

не удается открыть файл «имя_файла» [: причина]

BSCMAKE не удается открыть файл.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Файл заблокирован другим процессом. Если `reason` говорит **запрещено разрешение**, браузер использует этот файл. Закройте окно «Обзор» и повторите попытку сборки.

1. Диск переполнен.

1. Аппаратная ошибка.

1. Указанный выходной файл имеет имя, совпадающее с именем существующий подкаталог.