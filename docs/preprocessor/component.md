---
title: компонент | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.component
- component_CPP
dev_langs:
- C++
helpviewer_keywords:
- component pragma
- pragmas, component
ms.assetid: 7b66355e-3201-4c14-8190-f4a2a81a604a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5bb453e8fe9d21c25292c4e5f94de90dcc67676a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="component"></a>component
Контролирует сбор сведений о просмотре или зависимостях из файлов исходного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      #pragma component( browser, { on | off }[, references [, name ]] )  
#pragma component( minrebuild, on | off )  
#pragma component( mintypeinfo, on | off )  
```  
  
## <a name="remarks"></a>Примечания  
  
## <a name="browser"></a>Браузер  
 Можно включить или отключить сбор информации и задать игнорирование конкретных имен по мере сбора информации.  
  
 Включение и отключение сбора информации контролирует сбор сведений о просмотре, начиная с директивы pragma. Пример:  
  
```  
#pragma component(browser, off)  
```  
  
 предотвращает сбор информации о просмотре компилятором.  
  
> [!NOTE]
>  Чтобы включить сбор сведений о просмотре с помощью этой директивы #pragma [сначала необходимо включить сведения о просмотре](../build/reference/building-browse-information-files-overview.md).  
  
 **Ссылки** параметр можно использовать с или без *имя* аргумент. С помощью **ссылки** без *имя* включает или выключает сбор ссылок (другие сведения о просмотре по-прежнему собираются, однако). Пример:  
  
```  
#pragma component(browser, off, references)  
```  
  
 предотвращает сбор информации о ссылках компилятором.  
  
 С помощью **ссылки** с *имя* и **off** предотвращает ссылки на *имя* будут отображаться в окне просмотра информации. Используйте этот синтаксис, чтобы игнорировать ненужные имена и типы, уменьшая тем самым размер файлов со сведениями о просмотре. Пример:  
  
```  
#pragma component(browser, off, references, DWORD)  
```  
  
 игнорирует ссылки на **DWORD** с этого момента. Вы можете включить сбор ссылок на `DWORD` с использованием **на**:  
  
```  
#pragma component(browser, on, references, DWORD)  
```  
  
 Это единственный способ возобновить сбор ссылок на *имя*; необходимо явно включить любой *имя* , будут отключены.  
  
 Чтобы предотвратить расширение препроцессор *имя* (например расширение **NULL** для **0**), поместите его в кавычки:  
  
```  
#pragma component(browser, off, references, "NULL")  
```  
  
## <a name="minimal-rebuild"></a>Минимальная повторная сборка  
 Возможность минимальной повторной сборки Visual C++ требует, чтобы компилятор создавал и сохранял сведения о зависимости классов C++, что, в свою очередь, занимает место на диске. Чтобы сэкономить место на диске, можно использовать `#pragma component( minrebuild, off )` каждый раз, когда не требуется для сбора сведений о зависимостях для экземпляра в неизменяемых файлах заголовка. Вставить `#pragma component(minrebuild, on)` после неизменяемых классов, чтобы включить коллекцию зависимостей снова на.  
  
## <a name="reduce-type-information"></a>Уменьшение сведений о типах  
 **Mintypeinfo** снижает отладочную информацию для определенной области. Эти сведения имеют значительный объем, что влияет на размер PDB- и OBJ-файлов. Невозможно отладить классы и структуры в области параметра mintypeinfo. Использование параметра mintypeinfo поможет избежать следующего предупреждения.  
  
```  
LINK : warning LNK4018: too many type indexes in PDB "filename", discarding subsequent type information  
```  
  
 Дополнительные сведения см. в разделе [включение минимального перепостроения](../build/reference/gm-enable-minimal-rebuild.md) (/ Gm) параметр компилятора.  
  
## <a name="see-also"></a>См. также  
 [Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)