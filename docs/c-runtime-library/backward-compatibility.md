---
title: Обратная совместимость
ms.date: 11/04/2016
f1_keywords:
- c.programs
helpviewer_keywords:
- CRT, compatibility
- backward compatibility, C run-time libraries
- compatibility, C run-time libraries
- backward compatibility
ms.assetid: cc3175cf-97fd-492f-b329-5791aea63090
ms.openlocfilehash: f672f0601a9d20a726f90963265d08ec212dedce
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57744473"
---
# <a name="backward-compatibility"></a>Обратная совместимость

Для обеспечения совместимости между версиями продукта библиотека OLDNAMES.LIB сопоставляет старые имена с новыми именами. Например, `open` сопоставляется с `_open`. Явно выполнять компоновку с OLDNAMES.LIB необходимо только при компиляции со следующими параметрами командной строки:

- `/Zl` (опустить имя библиотеки по умолчанию из объектного файла) и `/Ze` (по умолчанию — использовать расширения Microsoft)

- `/link` (управление компоновщиком), `/NOD` (отключить поиск библиотеки по умолчанию) и `/Ze`

Дополнительные сведения о параметрах компилятора командной строки см. в [справочнике по компилятору](../build/reference/compiler-options.md).

## <a name="see-also"></a>См. также

[Совместимость](../c-runtime-library/compatibility.md)
