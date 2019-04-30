---
title: Ошибка вычислителя выражений CXX0033
ms.date: 11/04/2016
f1_keywords:
- CXX0033
helpviewer_keywords:
- CAN0033
- CXX0033
ms.assetid: 0bd62c5b-de89-481f-9b12-88fe84805afe
ms.openlocfilehash: 8563eb2fbc24c6ad8db639d2e227802412a16090
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397059"
---
# <a name="expression-evaluator-error-cxx0033"></a>Ошибка вычислителя выражений CXX0033

Ошибка в данных типа OMF

Исполняемый файл не имеет формат модулей допустимый объект (OMF), для отладки.

Эта ошибка идентична CAN0033.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Исполняемый файл не был создан компоновщиком, выпущенным с данной версией Visual C++. Повторно связать объектный код, с помощью текущей версии LINK.exe.

1. Возможно, файл .exe поврежден. Повторная компиляция и выполнить повторную компоновку программы.