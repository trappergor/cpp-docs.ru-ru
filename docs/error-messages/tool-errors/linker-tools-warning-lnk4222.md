---
title: Предупреждение средств компоновщика LNK4222
ms.date: 11/04/2016
f1_keywords:
- LNK4222
helpviewer_keywords:
- LNK4222
ms.assetid: b7bb1794-41fb-4c83-b9b0-59c0d786a7da
ms.openlocfilehash: f74379861ad04142fd78a8e307af165072c9cadd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183037"
---
# <a name="linker-tools-warning-lnk4222"></a>Предупреждение средств компоновщика LNK4222

экспортируемому символу "Symbol" не следует присваивать порядковый номер

Следующие символы не должны экспортироваться по порядковому номеру:

- `DllCanUnloadNow`

- `DllGetClassObject`

- `DllGetClassFactoryFromClassString`

- `DllInstall`

- `DllRegisterServer`

- `DllRegisterServerEx`

- `DllUnregisterServer`

Эти функции всегда находятся по имени с помощью `GetProcAddress`. Компоновщик предупреждает об этом типе экспорта, так как это может привести к увеличению изображения. Это может произойти, если диапазон порядковых номеров экспорта велик с относительно небольшими экспортами. Например,

```
EXPORTS
   DllGetClassObject   @1
   MyOtherAPI      @100
```

потребует 100 слотов в таблице адресов экспорта с 98 (2-99) просто заполнения. С другой стороны

```
EXPORTS
   DllGetClassObject
   MyOtherAPI      @100
```

потребуется два слота. (Имейте в виду, что можно также экспортировать с параметром компоновщика [/Export](../../build/reference/export-exports-a-function.md) .)
