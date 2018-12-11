---
title: Предупреждение командной строки D9035
ms.date: 12/10/2018
f1_keywords:
- D9035
helpviewer_keywords:
- D9035
ms.assetid: 6254f933-e37a-45ba-b860-1a870d1bc8e8
ms.openlocfilehash: 9c0a159dcf193b4ad016069bafd86c557e9e1281
ms.sourcegitcommit: 6990f842fefc27b522b15cf352f3517b319d78da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53248524"
---
# <a name="command-line-warning-d9035"></a>Предупреждение командной строки D9035

> параметр "*параметр*" является устаревшим и будет удален в будущем выпуске

## <a name="remarks"></a>Примечания

Вы указали параметр компилятора, которая будет удалена в будущей версии компилятора. Если предложенная замена *параметр*, это предупреждение сопровождается предупреждение [D9036](../../error-messages/tool-errors/command-line-warning-d9036.md).

Указанный параметр по-прежнему работает, но необходимо обновить конфигурацию построения. Таким образом проект, скорее всего, продолжить создание при обновлении компилятор.

## <a name="see-also"></a>См. также

[Нерекомендуемые и удаленные параметры компилятора](../../build/reference/compiler-options-listed-by-category.md#deprecated-and-removed-compiler-options)<br/>
[Предупреждение командной строки D9036](command-line-warning-d9036.md)