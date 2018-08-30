---
title: -HIGHENTROPYVA | Документация Майкрософт
ms.custom: ''
ms.date: 06/12/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /HIGHENTROPYVA
dev_langs:
- C++
helpviewer_keywords:
- HIGHENTROPYVA editbin option
- -HIGHENTROPYVA editbin option
- /HIGHENTROPYVA editbin option
ms.assetid: ef4b7c63-440d-40ca-b39d-edefb3217505
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5fec9314be9d69e2cb0af2a98884bd78de1ff679
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43202067"
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
