---
title: /HIGHENTROPYVA (поддержка 64-разрядной рандомизации ASLR)
ms.date: 06/12/2018
ms.assetid: fe35f9f7-d28e-4694-9aeb-a79db06168e0
ms.openlocfilehash: 5ecbbf8bbd8e74f80f2f5b2d7df0d2ef544112fc
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822006"
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

1. Откройте диалоговое окно **Окна свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** > **командной строки** страницу свойств.

1. В **Дополнительные параметры**, введите `/HIGHENTROPYVA` или `/HIGHENTROPYVA:NO`.

## <a name="see-also"></a>См. также

- [Справочник по компоновщику MSVC](linking.md)
- [Параметры компоновщика MSVC](linker-options.md)
- [/DYNAMICBASE](dynamicbase-use-address-space-layout-randomization.md)
- [/LARGEADDRESSAWARE](largeaddressaware-handle-large-addresses.md)
- [Способы защиты программного обеспечения для независимых поставщиков программного обеспечения Windows](https://msdn.microsoft.com/library/bb430720.aspx)
