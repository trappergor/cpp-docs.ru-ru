---
title: /HIGHENTROPYVA (поддержка 64-разрядной рандомизации ASLR)
ms.date: 06/12/2018
ms.assetid: fe35f9f7-d28e-4694-9aeb-a79db06168e0
ms.openlocfilehash: 8f8601d89e8456461aac3d91f9fd2cfda216d7f5
ms.sourcegitcommit: 31a443c9998cf5cfbaff00fcf815b133f55b2426
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "86373844"
---
# <a name="highentropyva-support-64-bit-aslr"></a>/HIGHENTROPYVA (поддержка 64-разрядной рандомизации ASLR)

Указывает, поддерживает ли исполняемый образ 64-разрядную технологию ASLR с высокой энтропией.

## <a name="syntax"></a>Синтаксис

> **/highentropyva**[**: нет**]

## <a name="remarks"></a>Remarks

**/Highentropyva** изменяет заголовок *исполняемого образа*, DLL-файла или EXE-файла, чтобы указать, может ли ASLR использовать все 64 разрядов адресного пространства. Если для исполняемого файла и всех модулей, от которых он зависит, задан этот параметр, то операционная система, поддерживающая 64-разрядную технологию, может переместить сегменты исполняемого образа во время загрузки, используя случайные адреса в 64-разрядном виртуальном адресном пространстве. Благодаря обширному адресному пространству злоумышленнику будет труднее догадаться о расположении определенной области в памяти.

По умолчанию **/highentropyva** включается для 64-разрядных исполняемых образов. Для этого параметра требуется [/LARGEADDRESSAWARE](largeaddressaware-handle-large-addresses.md), который также включен по умолчанию для 64-разрядных изображений. **/Highentropyva** не применяется к 32-разрядным исполняемым образам, где компоновщик игнорирует параметр. Чтобы явно отключить этот параметр, используйте **/highentropyva: No**.

Чтобы **/highentropyva** действовал во время загрузки, необходимо также включить [/DynamicBase](dynamicbase-use-address-space-layout-randomization.md) . **/DynamicBase** включен по умолчанию и требуется для включения ASLR в Windows Vista и более поздних операционных системах. В более ранних версиях Windows этот флаг игнорируется.

### <a name="to-set-this-linker-option-in-visual-studio"></a>Настройка этого параметра компоновщика в Visual Studio

1. Откройте диалоговое окно **Окна свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойств сборки в Visual Studio](../working-with-project-properties.md).

1. Перейдите на **Configuration Properties**  >  **Linker**  >  страницу свойства**командной строки** компоновщика свойств конфигурации.

1. В окне **Дополнительные параметры**введите `/HIGHENTROPYVA` или `/HIGHENTROPYVA:NO` .

## <a name="see-also"></a>См. также раздел

- [Справочник по компоновщику MSVC](linking.md)
- [Параметры компоновщика MSVC](linker-options.md)
- [/DYNAMICBASE](dynamicbase-use-address-space-layout-randomization.md)
- [/LARGEADDRESSAWARE](largeaddressaware-handle-large-addresses.md)
- [Средства защиты программного обеспечения Windows ISV](https://docs.microsoft.com/previous-versions/bb430720(v=msdn.10))
