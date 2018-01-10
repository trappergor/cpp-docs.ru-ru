---
title: "Соглашения об именовании библиотек | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NAFXCW.LIB [MFC]
- libraries [MFC], static
- coding conventions [MFC], MFC library names
- NAFXCWD.LIB [MFC]
- console applications [MFC], MFC library versions
- naming conventions [MFC], MFC object code libraries
- object code libraries, MFC naming conventions
- object code libraries
- conventions [MFC], MFC library names
- MFC libraries, naming conventions
ms.assetid: 39fe7d93-5a14-4c6a-b16c-bf318fa01278
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 14e217b3cfd9f3618046cf1a0ca825eb2e6492f2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="library-naming-conventions"></a>Соглашения об именовании библиотек
Библиотеки объектного кода для MFC, используйте следующие соглашения об именовании. Имена библиотек имеют форму  
  
 *u*AFX*c*W*d*. LIB  
  
 где курсивом строчные буквы являются заполнителями для спецификаторы, чьи значения показаны в следующей таблице:  
  
### <a name="library-naming-conventions"></a>Соглашения об именовании библиотек  
  
|Описатель|Значения и значения|  
|---------------|-------------------------|  
|*u*|(N) ANSI или Юникода (U)|  
|*c*|Тип программы для создания: C = all|  
|*d*|Отладка или выпуск: D = Debug; пропущен спецификатор для выпуска|  
  
 Значение по умолчанию — для построения отладки приложения Windows ANSI для платформ Intel: NAFXCWD.Lib. Включаются все библиотеки, которые перечислены в следующей таблице готовых в каталоге \atlmfc\lib.  
  
### <a name="static-link-library-naming-conventions"></a>Статическая библиотека, соглашения об именовании  
  
|Библиотека|Описание:|  
|-------------|-----------------|  
|NAFXCW.LIB|Статическая библиотека MFC, версии|  
|NAFXCWD.LIB|Статическая библиотека MFC, отладочная версия|  
|UAFXCW. LIB|Статическая библиотека MFC с поддержкой Юникода, в окончательной версии|  
|UAFXCWD. LIB|Статическая библиотека MFC с поддержкой Юникода, отладочная версия|  
  
> [!NOTE]
>  Если необходимо создать версию библиотеки, см. в файле Readme.Txt в каталоге \atlmfc\src\mfc. Этот файл описывает при помощи предоставленного файла makefile (NMAKE).  
  
 Дополнительные сведения см. в разделе [соглашения об именовании библиотек DLL MFC](../build/naming-conventions-for-mfc-dlls.md) и [Юникода версии библиотек MFC](../mfc/unicode-in-mfc.md).  
  
## <a name="see-also"></a>См. также  
 [Версии библиотек MFC](../mfc/mfc-library-versions.md)

