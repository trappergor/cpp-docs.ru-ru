---
title: Предупреждение средств компоновщика LNK4222
ms.date: 11/04/2016
f1_keywords:
- LNK4222
helpviewer_keywords:
- LNK4222
ms.assetid: b7bb1794-41fb-4c83-b9b0-59c0d786a7da
ms.openlocfilehash: 52a4fee532eb9997dcf013f95246b27fdffc4c20
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160410"
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