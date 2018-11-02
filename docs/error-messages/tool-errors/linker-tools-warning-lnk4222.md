---
title: Предупреждение средств компоновщика LNK4222
ms.date: 11/04/2016
f1_keywords:
- LNK4222
helpviewer_keywords:
- LNK4222
ms.assetid: b7bb1794-41fb-4c83-b9b0-59c0d786a7da
ms.openlocfilehash: 52a4fee532eb9997dcf013f95246b27fdffc4c20
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50563102"
---
# <a name="linker-tools-warning-lnk4222"></a>Предупреждение средств компоновщика LNK4222

экспортированному символу «символ» не следует назначать порядковый номер

Следующие символы не должны быть экспортированы по порядковому номеру:

- `DllCanUnloadNow`

- `DllGetClassObject`

- `DllGetClassFactoryFromClassString`

- `DllInstall`

- `DllRegisterServer`

- `DllRegisterServerEx`

- `DllUnregisterServer`

Эти функции всегда находятся по имени, с помощью `GetProcAddress`. Компоновщик предупреждает об этом типе экспорта, так как это может привести чтобы увеличить изображение. Это может произойти, если диапазон порядковых номеров экспортов велик с относительно небольшое количество экспортов. Например, примененная к объекту директива

```
EXPORTS
   DllGetClassObject   @1
   MyOtherAPI      @100
```

потребуется 100 областей в таблице экспорта адрес 98 из них просто заполнитель (2-99). С другой стороны

```
EXPORTS
   DllGetClassObject
   MyOtherAPI      @100
```

потребуется две области. (Имейте в виду, что можно также экспортировать [/EXPORT](../../build/reference/export-exports-a-function.md) параметр компоновщика.)