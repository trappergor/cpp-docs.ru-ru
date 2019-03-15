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
ms.openlocfilehash: 7f40841b82db9f46019ce2a96a61a1a0f622b6d5
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57813441"
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

**/Link** параметр и его параметры компоновщика должны располагаться после имен файлов и параметров CL. Пробел между **/link** и `linkeroptions`. Дополнительные сведения см. в разделе [ссылку компоновщика MSVC](linking.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Щелкните страницу свойств компоновщика.

1. Измените одно или несколько свойств.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- Этот параметр не может изменяться программно.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
