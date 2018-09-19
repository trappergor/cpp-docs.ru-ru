---
title: Неустранимая ошибка NMAKE U1073 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1073
dev_langs:
- C++
helpviewer_keywords:
- U1073
ms.assetid: d46bf2dd-400a-4802-9db2-f832e1c97f02
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c309ed94cd1c984406e0d21f0139e35c6e41d7d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053948"
---
# <a name="nmake-fatal-error-u1073"></a>Неустранимая ошибка NMAKE U1073

не знаю, как для имя_целевого_объекта»

Указанный целевой объект не существует, и нет команды для выполнения или применяемое правило.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки

1. Проверьте правильность написания имени целевого объекта.

1. Если *targetname* является псевдоцелью, укажите его в качестве целевого объекта в другом блоке описания.

1. Если *targetname* представляет собой вызов макроса, убедитесь, что оно не разворачивается в строку null.