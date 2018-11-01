---
title: Ошибка BSCMAKE BK1506
ms.date: 11/04/2016
f1_keywords:
- BK1506
helpviewer_keywords:
- BK1506
ms.assetid: f51f8cea-f8fc-4323-bcf2-b7bd119792ee
ms.openlocfilehash: d1f74a90657985a87accc13bc2b576c1d7fd5a4e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50554704"
---
# <a name="bscmake-error-bk1506"></a>Ошибка BSCMAKE BK1506

не удается открыть файл «имя_файла» [: причина]

BSCMAKE не удается открыть файл.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Файл заблокирован другим процессом. Если `reason` говорит **запрещено разрешение**, браузер использует этот файл. Закройте окно «Обзор» и повторите попытку сборки.

1. Диск переполнен.

1. Аппаратная ошибка.

1. Указанный выходной файл имеет имя, совпадающее с именем существующий подкаталог.