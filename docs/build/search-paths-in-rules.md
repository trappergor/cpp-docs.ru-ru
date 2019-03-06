---
title: Пути поиска в правилах
ms.date: 11/04/2016
helpviewer_keywords:
- search paths in NMAKE inference rules
- inference rules in NMAKE
- rules, inference
ms.assetid: 38feded6-536d-425d-bf40-fff3173a5506
ms.openlocfilehash: 9f45562c74db22dd1cfc493f86a4de5c96c48831
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57415920"
---
# <a name="search-paths-in-rules"></a>Пути поиска в правилах

```
{frompath}.fromext{topath}.toext:
   commands
```

## <a name="remarks"></a>Примечания

Правило вывода применимо к зависимости только в том случае, если пути, указанные в зависимости, точно соответствует путям правила вывода. Укажите каталог зависимого объекта, в *frompath* и целевого объекта каталога в *параметре topath*; пробелы не допускаются. Укажите только один путь для каждого расширения. Путь на одно расширение требуется указать путь на другой. Чтобы указать текущего каталога, используйте точку (.) или пустых фигурных скобок ({}). Макросы могут представлять *frompath* и *параметре topath*; они вызываются во время предварительной обработки.

## <a name="example"></a>Пример

### <a name="code"></a>Код

```
{dbi\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUDBI) $<

{ilstore\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<

{misc\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{misc\}.c{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<

{msf\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<

{bsc\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{mre\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{namesrvr\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{src\cvr\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<
```

## <a name="see-also"></a>См. также

[Определение правила](../build/defining-a-rule.md)
