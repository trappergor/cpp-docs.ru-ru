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
ms.openlocfilehash: b2ff9929de74d99fbc45e4f4ff38fd6b939697bc
ms.sourcegitcommit: 31a443c9998cf5cfbaff00fcf815b133f55b2426
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "86373831"
---
# <a name="highentropyva"></a>/HIGHENTROPYVA

Указывает, поддерживает ли исполняемый образ 64-разрядную технологию ASLR с высокой энтропией.

## <a name="syntax"></a>Синтаксис

> **/highentropyva**[**: нет**]

## <a name="remarks"></a>Remarks

Этот параметр изменяет заголовок *исполняемого образа*, DLL-файла или EXE-файла, чтобы указать, поддерживается ли ASLR с 64 бит/с. Если для исполняемого файла и всех модулей, от которых он зависит, задан этот параметр, то операционная система, поддерживающая 64-разрядную технологию, может переместить сегменты исполняемого образа во время загрузки, используя случайные адреса в 64-разрядном виртуальном адресном пространстве. Благодаря обширному адресному пространству злоумышленнику будет труднее догадаться о расположении определенной области в памяти.

По умолчанию компоновщик включает **/highentropyva** для 64-разрядных исполняемых образов. Для этого параметра требуется [/LARGEADDRESSAWARE](largeaddressaware.md), который также включен по умолчанию для 64-разрядных изображений. **/Highentropyva** не применяется к 32-разрядным исполняемым образам, в которых параметр игнорируется. Чтобы явно отключить этот параметр, используйте **/highentropyva: No**. Чтобы этот параметр действовал, также необходимо задать параметр [/DynamicBase](dynamicbase.md) .

## <a name="see-also"></a>См. также

- [Параметры EDITBIN](editbin-options.md)
- [/DYNAMICBASE](dynamicbase.md)
- [Средства защиты программного обеспечения Windows ISV](https://docs.microsoft.com/previous-versions/bb430720(v=msdn.10))
