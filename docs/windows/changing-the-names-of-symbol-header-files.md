---
title: Изменение имен файлов символов заголовков | Документы Microsoft
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
- resource files, multiple
- Resource Includes dialog box
- symbol header files, changing names
- symbol header files
- header files, changing names
- names [C++], symbol header files
- symbols, symbol header files
- Resource.h
ms.assetid: b948284a-7899-402e-ab12-9f2c8480ca9d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 953ac59958748bd58fa7e9027c595bf7905e5f27
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="changing-the-names-of-symbol-header-files"></a>Изменение имен файлов символов заголовков
Обычно все определения символов сохраняются в файле Resource.h. Однако может возникнуть необходимость изменить имя этого включаемого файла, чтобы, например, работать с несколькими файлами ресурсов, расположенными в одном каталоге.  
  
### <a name="to-change-the-name-of-the-resource-symbol-header-file"></a>Изменение имени файла символов заголовков ресурсов  
  
1.  В [представление ресурсов](../windows/resource-view-window.md), щелкните правой кнопкой мыши RC-файл и выберите [включения ресурсов](../windows/resource-includes-dialog-box.md) в контекстном меню.  
  
    > [!NOTE]
    >  Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  В **файла символов заголовков** введите новое имя включаемого файла.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.*  
  
 Требования  
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Просмотр символов ресурсов](../windows/viewing-resource-symbols.md)   
 [Стандартные идентификаторы символов](../windows/predefined-symbol-ids.md)