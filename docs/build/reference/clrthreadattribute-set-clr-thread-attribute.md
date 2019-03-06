---
title: /CLRTHREADATTRIBUTE (Установка атрибута потока среды CLR)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.CLRThreadAttribute
helpviewer_keywords:
- /CLRTHREADATTRIBUTE linker option
- -CLRTHREADATTRIBUTE linker option
ms.assetid: 4907e9ef-5031-446c-aecf-0a0b32fae1e8
ms.openlocfilehash: f1a637f74cf1da608149779821a25340d35f8739
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57417155"
---
# <a name="clrthreadattribute-set-clr-thread-attribute"></a>/CLRTHREADATTRIBUTE (Установка атрибута потока среды CLR)

Явно задавать атрибут потока для точки входа CLR-программы.

## <a name="syntax"></a>Синтаксис

```
/CLRTHREADATTRIBUTE:{STA|MTA|NONE}
```

#### <a name="parameters"></a>Параметры

**АГЕНТ ПЕРЕДАЧИ СООБЩЕНИЙ**<br/>
Применяет атрибут MTAThreadAttribute к точке входа программы.

**НЕТ**<br/>
Совпадает со значением, не указывая /CLRTHREADATTRIBUTE.  Позволяет Common Language Runtime (CLR) задайте атрибут потока по умолчанию.

**STA**<br/>
Применяет атрибут STAThreadAttribute к точке входа программы.

## <a name="remarks"></a>Примечания

Установка атрибута потока допустим только при построении .exe, как это влияет на точку входа для основного потока.

При использовании точки входа по умолчанию ("main" или "wmain, например") укажите модель потоков с помощью /CLRTHREADATTRIBUTE или поместив threading (STAThreadAttribute или MTAThreadAttribute) для атрибута функцию входа по умолчанию.

Если вы используете это точка входа не по умолчанию, укажите потоковой модели при помощи /CLRTHREADATTRIBUTE или поместив threading атрибут функцию входа не по умолчанию, а затем укажите точку входа не по умолчанию с [/Entry](../../build/reference/entry-entry-point-symbol.md) .

Если потоковая модель, указанная в исходном коде, не совпадает с потоковой моделью, указанной с помощью /CLRTHREADATTRIBUTE, компоновщик будет игнорировать атрибут/CLRTHREADATTRIBUTE и примените потоковой моделью, указанной в исходном коде.

Будет необходимо использовать однопоточную, например, если COM-объект, который использует однопоточная размещаются CLR-программы.  Если CLR-программа использует многопоточность, он не может разместить объект COM, который использует однопоточная.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Разверните узел **Свойства конфигурации**.

1. Разверните **компоновщика** узла.

1. Выберите **Дополнительно** страницу свойств.

1. Изменить **атрибута потока среды CLR** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRThreadAttribute%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)
