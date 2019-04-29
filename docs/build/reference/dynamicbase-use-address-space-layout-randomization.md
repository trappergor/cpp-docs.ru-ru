---
title: /DYNAMICBASE (использование технологии Address Space Layout Randomization (ASRL))
ms.date: 06/12/2018
f1_keywords:
- VC.Project.VCLinkerTool.RandomizedBaseAddress
helpviewer_keywords:
- -DYNAMICBASE linker option
- /DYNAMICBASE linker option
- DYNAMICBASE linker option
ms.assetid: 6c0ced8e-fe9c-4b63-b956-eb8a55fbceb2
ms.openlocfilehash: a3495de3ec72bcac78cdee2f5f3265864e7a2932
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62293073"
---
# <a name="dynamicbase-use-address-space-layout-randomization"></a>/DYNAMICBASE (использование технологии Address Space Layout Randomization (ASRL))

Указывает, следует ли создавать исполняемый образ, который может быть случайным образом переместить во время загрузки с помощью функции Windows, впервые появившаяся в Windows Vista адрес макета пространства randomization (ASLR).

## <a name="syntax"></a>Синтаксис

> **/DYNAMICBASE**[**:NO**]

## <a name="remarks"></a>Примечания

**/DYNAMICBASE** параметр изменяет заголовок *исполняемый образ*, файл .dll или .exe, чтобы указать, использует ли приложение следует случайным образом переместить во время загрузки и включает виртуальный адрес случайный выбор срока выделения, что влияет на расположение виртуальной памяти кучи, стеки и выделения памяти для операционной системы. **/DYNAMICBASE** параметр применяется к 32-разрядных и 64-разрядные образы. ASLR поддерживается в Windows Vista и более поздних операционных системах. Параметр обрабатывается в более ранних операционных систем.

По умолчанию **/DYNAMICBASE** включен. Чтобы отключить этот параметр, используйте **/DYNAMICBASE:NO**. **/DYNAMICBASE** параметр является обязательным для [/highentropyva](highentropyva-support-64-bit-aslr.md) параметр вступил в силу.

### <a name="to-set-this-linker-option-in-visual-studio"></a>Настройка этого параметра компоновщика в Visual Studio

1. Откройте диалоговое окно **Окна свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** > **Дополнительно** страницу свойств.

1. Изменить **базового адреса в случайном порядке** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RandomizedBaseAddress%2A>.

## <a name="see-also"></a>См. также

- [Справочник по компоновщику MSVC](linking.md)
- [Параметры компоновщика MSVC](linker-options.md)
- [/HIGHENTROPYVA](highentropyva-support-64-bit-aslr.md)
- [Способы защиты программного обеспечения для независимых поставщиков программного обеспечения Windows](https://msdn.microsoft.com/library/bb430720.aspx)