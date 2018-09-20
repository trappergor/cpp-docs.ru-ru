---
title: Изменение имен файлов символов заголовков | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.changing.header
dev_langs:
- C++
helpviewer_keywords:
- resource files [C++], multiple
- Resource Includes dialog box [C++]
- symbol header files [C++], changing names
- symbols [C++], symbol header files
- Resource.h
ms.assetid: b948284a-7899-402e-ab12-9f2c8480ca9d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 626fb3a7421414355d98a680d5647a494de26594
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374404"
---
# <a name="changing-the-names-of-symbol-header-files"></a>Изменение имен файлов символов заголовков

Обычно все определения символов сохраняются в `Resource.h`. Однако может возникнуть необходимость изменить имя этого включаемого файла, чтобы, например, работать с несколькими файлами ресурсов, расположенными в одном каталоге.

### <a name="to-change-the-name-of-the-resource-symbol-header-file"></a>Изменение имени файла символов заголовков ресурсов

1. В [представление ресурсов](../windows/resource-view-window.md), щелкните правой кнопкой мыши RC-файл и выберите пункт [включения ресурсов](../windows/resource-includes-dialog-box.md) в контекстном меню.

   > [!NOTE]
   > Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).

2. В **файла символов заголовков** введите новое имя включаемого файла.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*.

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Просмотр символов ресурсов](../windows/viewing-resource-symbols.md)<br/>
[Стандартные идентификаторы символов](../windows/predefined-symbol-ids.md)