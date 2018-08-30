---
title: / HIGHENTROPYVA (поддержка 64-разрядной рандомизации ASLR) | Документация Майкрософт
ms.custom: ''
ms.date: 06/12/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: fe35f9f7-d28e-4694-9aeb-a79db06168e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 66fe8f20631d576264eab836f822a414c1244d5b
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43223423"
---
# <a name="highentropyva-support-64-bit-aslr"></a>/HIGHENTROPYVA (поддержка 64-разрядной рандомизации ASLR)

Указывает, поддерживает ли исполняемый образ 64-разрядную технологию ASLR с высокой энтропией.

## <a name="syntax"></a>Синтаксис

> **/ HIGHENTROPYVA**[**: НЕТ**]

## <a name="remarks"></a>Примечания

**/ HIGHENTROPYVA** изменяет заголовок *исполняемый образ*, DLL-файл или файл .exe, чтобы указать, может ли ASLR использовать все 64-разрядное адресное пространство. Если для исполняемого файла и всех модулей, от которых он зависит, задан этот параметр, то операционная система, поддерживающая 64-разрядную технологию, может переместить сегменты исполняемого образа во время загрузки, используя случайные адреса в 64-разрядном виртуальном адресном пространстве. Благодаря обширному адресному пространству злоумышленнику будет труднее догадаться о расположении определенной области в памяти.

По умолчанию **/highentropyva** включен для 64-разрядных исполняемых образов. Этот параметр требует [/LARGEADDRESSAWARE](largeaddressaware-handle-large-addresses.md), также включена по умолчанию для 64-разрядных образов. **/ HIGHENTROPYVA** неприменим к 32-разрядных исполняемых образов, где игнорирует параметр в компоновщик. Чтобы явно отключить этот параметр, используйте **/highentropyva: no**.

Для **/highentropyva** действовала во время загрузки, [/DYNAMICBASE](dynamicbase-use-address-space-layout-randomization.md) также должна быть включена. **/ DYNAMICBASE** включена по умолчанию и необходимо включить технологию ASLR в Windows Vista и более поздних операционных системах. Более ранних версиях Windows игнорируют этот флажок.

### <a name="to-set-this-linker-option-in-visual-studio"></a>Настройка этого параметра компоновщика в Visual Studio

1. Откройте диалоговое окно **Окна свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** > **командной строки** страницу свойств.

1. В **Дополнительные параметры**, введите `/HIGHENTROPYVA` или `/HIGHENTROPYVA:NO`.

## <a name="see-also"></a>См. также

- [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)
- [Параметры компоновщика](../../build/reference/linker-options.md)
- [/DYNAMICBASE](dynamicbase-use-address-space-layout-randomization.md)
- [/LARGEADDRESSAWARE](largeaddressaware-handle-large-addresses.md)
- [Способы защиты программного обеспечения для независимых поставщиков программного обеспечения Windows](https://msdn.microsoft.com/library/bb430720.aspx)
