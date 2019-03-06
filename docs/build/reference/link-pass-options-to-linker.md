---
title: /link (Передача параметров компоновщику)
ms.date: 11/04/2016
f1_keywords:
- /link
helpviewer_keywords:
- /link compiler option [C++]
- pass options to linker
- link compiler option [C++]
- linker [C++], passing options to
- -link compiler option [C++]
- cl.exe compiler [C++], passing options to linker
ms.assetid: 16902a94-c094-4328-841f-3ac94ca04848
ms.openlocfilehash: f5e57a19f337653cdab6f66404b9458e1e7fed0d
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57412839"
---
# <a name="link-pass-options-to-linker"></a>/link (Передача параметров компоновщику)

Передает один или несколько параметров компоновщика в компоновщик.

## <a name="syntax"></a>Синтаксис

```
/link linkeroptions
```

## <a name="arguments"></a>Аргументы

*linkeroptions*<br/>
Параметр компоновщика или параметры для передачи в компоновщик.

## <a name="remarks"></a>Примечания

**/Link** параметр и его параметры компоновщика должны располагаться после имен файлов и параметров CL. Пробел между **/link** и `linkeroptions`. Дополнительные сведения см. в разделе [параметры компоновщика](../../build/reference/setting-linker-options.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Щелкните страницу свойств компоновщика.

1. Измените одно или несколько свойств.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- Этот параметр не может изменяться программно.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)
