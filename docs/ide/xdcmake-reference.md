---
title: Справочник по XDCMake | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- xdcmake
dev_langs:
- C++
helpviewer_keywords:
- xdcmake program
ms.assetid: 14e65747-d000-4343-854b-8393bf01cbac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 383347dc5cd1ce0dcadff6bdee802b90fd52e85d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
 Программа xdcmake `input_filename options`  
  
## <a name="parameters"></a>Параметры  
 Здесь:  
  
 `input_filename`  
 Имя файла XDC-файлах, используемых в качестве входных для xdcmake.exe. Укажите один или несколько файлов .xdc или используйте *.xdc для использования всех XDC-файлы в текущем каталоге.  
  
 `options`  
 Ноль или несколько из следующих действий:  
  
|Параметр|Описание|  
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