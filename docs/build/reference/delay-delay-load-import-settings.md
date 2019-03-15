---
title: /DELAY (параметры отложенной загрузки импортов)
ms.date: 11/04/2016
f1_keywords:
- /delay
- VC.Project.VCLinkerTool.DelayNoBind
- VC.Project.VCLinkerTool.SupportUnloadOfDelayLoadedDLL
- VC.Project.VCLinkerTool.DelayUnload
helpviewer_keywords:
- delayed loading of DLLs, /DELAY option
- DELAY linker option
- /DELAY linker option
- -DELAY linker option
ms.assetid: 9334b332-cc58-4dae-b10f-a4c75972d50c
ms.openlocfilehash: d3c32ba04cbad509ff2819020a35102698d6ceb3
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57821343"
---
# <a name="delay-delay-load-import-settings"></a>/DELAY (параметры отложенной загрузки импортов)

```
/DELAY:UNLOAD
/DELAY:NOBIND
```

## <a name="remarks"></a>Примечания

Параметр/DELAY управляет [отложенной загрузки](linker-support-for-delay-loaded-dlls.md) библиотек DLL:

- Квалификатор UNLOAD предписывает вспомогательной функции отложенной загрузки поддерживать явную выгрузку DLL. Таблица адресов импорта (IAT) восстанавливается в своем первоначальном виде; это приводит к тому, что указатели IAT становятся недействительными и перезаписываются.

   Если вы не выберете UNLOAD, любой вызов [FUnloadDelayLoadedDLL](explicitly-unloading-a-delay-loaded-dll.md) завершится ошибкой.

- Квалификатор NOBIND предписывает компоновщику не включать связываемую таблицу IAT в окончательный образ. По умолчанию задано создание связываемой таблицы IAT для библиотек DLL, загружаемых с задержкой. Полученный в результате образ не может быть статически привязан. (Образы с привязываемыми таблицами IAT могут быть статически привязаны перед выполнением.) См. в разделе [/BIND](bind.md).

   Если библиотека DLL привязана, вспомогательная функция будет пытаться использовать данные привязки вместо вызова метода [GetProcAddress](/windows/desktop/api/libloaderapi/nf-libloaderapi-getprocaddress) на каждого из импортов, на который указывает ссылка. Если отметка времени или предпочтительный адрес не соответствуют таковым в загружаемой библиотеке DLL, то вспомогательная функция будет предполагать, что привязанная таблица IAT устарела, и продолжать обработку так, будто привязанной таблицы IAT не существует.

   Применение квалификатора NOBIND приведет к увеличению образа программы, но зато может уменьшить время загрузки библиотеки DLL. Если привязка библиотеки DLL не предполагалась, то NOBIND предотвратит создание привязанной таблицы IAT.

Чтобы указать библиотеки DLL с отложенной загрузкой, используйте [/DELAYLOAD](delayload-delay-load-import.md) параметр.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Разверните **свойства конфигурации**, **компоновщика**, а затем выберите **Дополнительно**.

1. Изменить **Отложенно загружаемые DLL** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
