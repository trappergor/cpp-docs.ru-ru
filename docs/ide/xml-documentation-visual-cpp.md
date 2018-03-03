---
title: "XML-документации (Visual C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- XML documentation
- XML, documentation comments in source code
- comments, C++ source code files
- /// delimiter for C++ documentation
ms.assetid: a1aec1c5-b2d1-4c74-83ae-1dbbbb76b506
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 17853a43d3a94be779b659b0da825467fa66f61c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="xml-documentation-visual-c"></a>Документация XML (Visual C++)
В Visual C++ можно добавить комментарии в исходный код, который будет обработан в XML-файл. Затем этот файл можно входных данных для процесса, создает документацию по классам в коде.  
  
 В файле с исходным кодом Visual C++ комментарии документации XML должен находиться непосредственно перед определением метода или типа. Комментарии могут быть использованы для заполнения подсказке кратких сведений Intellisense в следующих сценариях:  
  
1.  При компиляции кода как компонент среды выполнения Windows с сопутствующий файл .winmd  
  
2.  Если исходный код, включенный в текущем проекте  
  
3.  в библиотеке, объявления и реализации типов находятся в том же файле заголовка  
  
> [!NOTE]
>  В текущем выпуске комментарии к коду, не обрабатываются на шаблоны или каком-либо, содержащее тип шаблона (например, функция, принимающая параметр как шаблон). Такие комментарии приведет к неопределенному поведению.  
  
 Дополнительные сведения о создании XML-файла в комментарии документации в следующих разделах.  
  
|Сведения|См.|  
|---------------------------|---------|  
|Параметры компилятора, используемые|[/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)|  
|Теги, которые можно использовать для предоставления часто используемым функциям в документации|[Рекомендуемые теги для комментариев документации](../ide/recommended-tags-for-documentation-comments-visual-cpp.md)|  
|Идентификатор строки, компилятор создает для идентификации конструкции в коде|[Обработка XML-файла](../ide/dot-xml-file-processing.md)|  
|Способ разделения тегов документации|[Разделители для тегов документации Visual C++](../ide/delimiters-for-visual-cpp-documentation-tags.md)|  
|Создание XML-файл из одного или нескольких файлов .xdc.|[Справочник по XDCMake](../ide/xdcmake-reference.md)|  
|Ссылки на сведения о XML, как оно относится к областям Visual Studio|[XML в Visual Studio](/visualstudio/xml-tools/xml-tools-in-visual-studio)|  
  
 Если вам нужно поместить специальные символы XML в текст комментария документации, необходимо использовать сущностей XML или раздела CDATA.  
  
## <a name="see-also"></a>См. также  
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)