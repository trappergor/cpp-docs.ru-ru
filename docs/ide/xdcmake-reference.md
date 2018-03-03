---
title: "Справочник по XDCMake | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xdcmake
dev_langs:
- C++
helpviewer_keywords:
- xdcmake program
ms.assetid: 14e65747-d000-4343-854b-8393bf01cbac
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ea635d701b4dea2471067072083d9568f11f3d82
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="xdcmake-reference"></a>Справочник по XDCMake
xdcmake.exe — это программа, которая компилирует XDC-файлы в XML-файл. XDC-файл создается компилятором Visual C++ для каждого файла исходного кода при компиляции исходного кода с [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) и когда файл исходного кода содержит комментарии, помеченные XML-теги.  
  
### <a name="to-use-xdcmakeexe-in-the-visual-studio-development-environment"></a>Чтобы использовать xdcmake.exe в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../ide/working-with-project-properties.md).  
  
2.  Откройте **свойства конфигурации** папки.  
  
3.  Нажмите кнопку **комментариев XML-документа** страницу свойств.  
  
> [!NOTE]
>  Параметры xdcmake.exe в командной строке отличаются от параметров, при использовании xdcmake.exe в среде разработки (страницы свойств). Сведения об использовании xdcmake.exe в среде разработки см. в разделе [страницы свойств средства создания документа XML](../ide/xml-document-generator-tool-property-pages.md).  
  
## <a name="syntax"></a>Синтаксис  
 Программа xdcmake`input_filename options`  
  
## <a name="parameters"></a>Параметры  
 Здесь:  
  
 `input_filename`  
 Имя файла XDC-файлах, используемых в качестве входных для xdcmake.exe. Укажите один или несколько файлов .xdc или используйте *.xdc для использования всех XDC-файлы в текущем каталоге.  
  
 `options`  
 Ноль или несколько из следующих действий:  
  
|Параметр|Описание:|  
|------------|-----------------|  
|/?, / help|Отображение справки для xdcmake.exe.|  
|/ Assembly:*имя файла*|Вы можете задать значение \<сборки > тегов в XML-файле.  По умолчанию значение \<сборки > тег является таким же, как имя файла XML-файла.|  
|/nologo|Подавлять сообщения об авторских правах.|  
|/ out:*имя файла*|Позволяет указать имя XML-файла.  По умолчанию имя XML-файла является имя первого XDC-файла, обрабатываемых xdcmake.exe.|  
  
## <a name="remarks"></a>Примечания  
 Visual Studio будет вызывать xdcmake.exe автоматически при построении проекта. Можно также вызвать xdcmake.exe из командной строки.  
  
 В разделе [Рекомендуемые теги для комментариев документации](../ide/recommended-tags-for-documentation-comments-visual-cpp.md) Дополнительные сведения о добавлении комментариев документации в файлах исходного кода.  
  
## <a name="see-also"></a>См. также  
 [Документация XML](../ide/xml-documentation-visual-cpp.md)