---
title: Неустранимая ошибка NMAKE U1073
ms.date: 11/04/2016
f1_keywords:
- U1073
helpviewer_keywords:
- U1073
ms.assetid: d46bf2dd-400a-4802-9db2-f832e1c97f02
ms.openlocfilehash: 2aa02fd86906bd545373a313fa5e6e409ffb3cf9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366937"
---
# <a name="nmake-fatal-error-u1073"></a>Неустранимая ошибка NMAKE U1073

не знаю, как для имя_целевого_объекта»

Указанный целевой объект не существует, и нет команды для выполнения или применяемое правило.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки

1. Проверьте правильность написания имени целевого объекта.

1. Если *targetname* является псевдоцелью, укажите его в качестве целевого объекта в другом блоке описания.

1. Если *targetname* представляет собой вызов макроса, убедитесь, что оно не разворачивается в строку null.