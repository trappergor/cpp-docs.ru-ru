---
title: Ошибка вычислителя выражений CXX0033 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0033
dev_langs:
- C++
helpviewer_keywords:
- CAN0033
- CXX0033
ms.assetid: 0bd62c5b-de89-481f-9b12-88fe84805afe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 04f37b53c30d36a43d339132bfd9baca3e5ec70c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057203"
---
# <a name="expression-evaluator-error-cxx0033"></a>Ошибка вычислителя выражений CXX0033

Ошибка в данных типа OMF

Исполняемый файл не имеет формат модулей допустимый объект (OMF), для отладки.

Эта ошибка идентична CAN0033.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Исполняемый файл не был создан компоновщиком, выпущенным с данной версией Visual C++. Повторно связать объектный код, с помощью текущей версии LINK.exe.

1. Возможно, файл .exe поврежден. Повторная компиляция и выполнить повторную компоновку программы.