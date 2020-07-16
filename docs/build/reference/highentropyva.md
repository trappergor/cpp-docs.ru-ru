---
title: /HIGHENTROPYVA
ms.date: 06/12/2018
f1_keywords:
- /HIGHENTROPYVA
helpviewer_keywords:
- HIGHENTROPYVA editbin option
- -HIGHENTROPYVA editbin option
- /HIGHENTROPYVA editbin option
ms.assetid: ef4b7c63-440d-40ca-b39d-edefb3217505
ms.openlocfilehash: 1adc12c0673764460b4af5eb7cf3b394d9666e81
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2020
ms.locfileid: "86404104"
---
# <a name="highentropyva"></a>/HIGHENTROPYVA

Указывает, поддерживает ли исполняемый образ 64-разрядную технологию ASLR с высокой энтропией.

## <a name="syntax"></a>Синтаксис

> **`/HIGHENTROPYVA`**[**`:NO`**]

## <a name="remarks"></a>Remarks

Этот параметр изменяет заголовок файла *исполняемого образа* (например, *`.dll`* *`.exe`* файла или), чтобы указать поддержку ASLR с 64-битным адресом. Чтобы получить результат, задайте параметр как для исполняемого файла, так и для всех модулей, от которых он зависит. Затем операционные системы, поддерживающие 64-разрядный ASLR, могут перераспределять сегменты исполняемого образа во время загрузки, используя случайные 64-битные виртуальные адреса. Благодаря обширному адресному пространству злоумышленнику будет труднее догадаться о расположении определенной области в памяти.

По умолчанию компоновщик поддерживает **`/HIGHENTROPYVA`** 64-разрядные исполняемые образы. Этот параметр требует [`/DYNAMICBASE`](dynamicbase.md) и [`/LARGEADDRESSAWARE`](largeaddressaware.md) , и, которые также включены по умолчанию для 64-разрядных изображений. **`/HIGHENTROPYVA`** не применяется к 32-разрядным исполняемым образам, в которых параметр игнорируется. Чтобы явно отключить этот параметр, используйте **`/HIGHENTROPYVA:NO`** .

## <a name="see-also"></a>См. также

[Параметры EDITBIN](editbin-options.md)\
[`/DYNAMICBASE`](dynamicbase.md)\
[`/LARGEADDRESSAWARE`](largeaddressaware.md)\
[Средства защиты программного обеспечения Windows ISV](https://docs.microsoft.com/previous-versions/bb430720(v=msdn.10))
