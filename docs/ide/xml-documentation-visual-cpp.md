---
title: XML-документации (Visual C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- XML documentation
- XML, documentation comments in source code
- comments, C++ source code files
- /// delimiter for C++ documentation
ms.assetid: a1aec1c5-b2d1-4c74-83ae-1dbbbb76b506
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9ee19c51c04fa32ab3c2f1810bb963b22ec7e890
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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