---
title: 'Как: интеграция пользовательских средств в свойства проекта | Документы Microsoft'
ms.custom: ''
ms.date: 04/27/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- msbuild.cpp.howto.integratecustomtools
dev_langs:
- C++
helpviewer_keywords:
- 'msbuild (c++), howto: integrate custom tools'
ms.assetid: f32d91a4-44e9-4de3-aa9a-1c7f709ad2ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 00482aa2b4b700d15e46d0741e76dd17afc28419
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-integrate-custom-tools-into-the-project-properties"></a>Практическое руководство. Интеграция пользовательских средств в свойства проекта
Можно добавить параметры пользовательских средств в Visual Studio **страницы свойств** окна путем создания базового файла схемы XML.  
  
 **Свойства конфигурации** раздел **страницы свойств** окне отображаются группы параметров, которые называются *правила*. Каждое правило содержит параметры для средства или группы функций. Например **компоновщика** правило содержит параметры для средства компоновщика. Параметры в правиле можно разделить на *категории*.  
  
 В этом документе объясняется, как создать файл в заданном каталоге, который содержит свойства для пользовательского средства, чтобы свойства загружаются при запуске Visual Studio. Сведения об изменении файла см. в разделе [часть 2 расширяемость платформы](http://go.microsoft.com/fwlink/p/?linkid=191489) в блоге группы проекта Visual Studio.  
  
### <a name="to-add-or-change-project-properties"></a>Чтобы добавить или изменить свойства проекта  
  
1.  В редакторе XML Создание XML-файла.  
  
2.  Сохраните файл в Visual Studio 2017 `VCTargets\1033` папки. Будет иметь другой путь для каждого выпуска Visual Studio 2017 г., установленного и каждого языка. Например, путь к папке для Visual Studio Enterprise edition на английском языке является `%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033`. Измените путь для языка и выпуска Visual Studio. Каждое правило в **страницы свойств** окна, представленного в XML-файл в этой папке. Убедитесь, что файл уникальное имя в папке.  
  
3.  Скопируйте содержимое `%ProgramFiles%\Microsoft Visual Studio\2017\<VS Edition>\Common7\IDE\VC\VCTargets\<LCID>\cl.xml`, закройте ее без сохранения изменений, а затем вставьте содержимое в новый XML-файл. Можно использовать любой файл схемы XML - это лишь одно, который может использоваться, чтобы начать с шаблона.  
  
4.  В новый XML-файл измените содержимое в соответствии со своими требованиями. Убедитесь в том изменить **имя правила** и **Rule.DisplayName** в верхней части файла.  
  
5.  Сохраните изменения и закройте файл.  
  
6.  XML-файлы в `%ProgramFiles%\Microsoft Visual Studio\2017\<VS Edition>\Common7\IDE\VC\VCTargets\<LCID>` загружаются при запуске Visual Studio. Таким образом Чтобы проверить новый файл, перезапустите Visual Studio.  
  
7.  В **обозревателе решений**, щелкните правой кнопкой мыши проект и нажмите кнопку **свойства**. В **страницы свойств** в левой области окна убедитесь, что новый узел с именем своего правила.  
  
## <a name="see-also"></a>См. также  
 [MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)
