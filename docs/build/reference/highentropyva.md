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
ms.openlocfilehash: 90d3c868eaab85e3b1a2a416c9aa14b0e27ec8f9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50603987"
---
# <a name="highentropyva"></a>/HIGHENTROPYVA

Указывает, поддерживает ли исполняемый образ 64-разрядную технологию ASLR с высокой энтропией.

## <a name="syntax"></a>Синтаксис

> **/ HIGHENTROPYVA**[**: НЕТ**]

## <a name="remarks"></a>Примечания

Этот параметр изменяет заголовок *исполняемый образ*, DLL-файл или файл .exe, чтобы указать, поддерживается ли ASLR с 64-разрядными адресами. Если для исполняемого файла и всех модулей, от которых он зависит, задан этот параметр, то операционная система, поддерживающая 64-разрядную технологию, может переместить сегменты исполняемого образа во время загрузки, используя случайные адреса в 64-разрядном виртуальном адресном пространстве. Благодаря обширному адресному пространству злоумышленнику будет труднее догадаться о расположении определенной области в памяти.

По умолчанию компоновщик включает **/highentropyva** для 64-разрядных исполняемых образов. Этот параметр требует [/LARGEADDRESSAWARE](largeaddressaware.md), также включена по умолчанию для 64-разрядных образов. **/ HIGHENTROPYVA** неприменим к 32-разрядных исполняемых образов, где параметр игнорируется. Чтобы явно отключить этот параметр, используйте **/highentropyva: no**. Эта возможность оказывать влияние [/DYNAMICBASE](dynamicbase.md) параметр также должен быть установлен.

## <a name="see-also"></a>См. также

- [Параметры EDITBIN](editbin-options.md)
- [/DYNAMICBASE](dynamicbase.md)
- [Способы защиты программного обеспечения для независимых поставщиков программного обеспечения Windows](https://msdn.microsoft.com/library/bb430720.aspx)
