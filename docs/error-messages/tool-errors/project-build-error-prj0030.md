---
title: Ошибка построения проекта PRJ0030
ms.date: 11/04/2016
f1_keywords:
- PRJ0030
helpviewer_keywords:
- PRJ0030
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
ms.openlocfilehash: 3675c3796ae37df848e458aa2db665d8c4aa7766
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80192514"
---
# <a name="project-build-error-prj0030"></a>Ошибка построения проекта PRJ0030

Ошибка расширения макроса. Оценка рекурсии для $ (макрос) превысила 32 уровней.

Эта ошибка вызвана рекурсией в макросах. Например, если задать свойство **промежуточного каталога** (см. Общие сведения о [странице свойств (Project)](../../build/reference/general-property-page-project.md)) в $ (IntDir), то будет возникнет рекурсия.

Чтобы устранить эту ошибку, не определяйте макросы или свойства с точки зрения макросов, которые они используют для определения.
