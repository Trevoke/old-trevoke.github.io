---
layout: post
status: publish
published: true
title: Recursively iterate through every file/subfolder  - VBScript
author: Trevoke
author_login: Trevoke
author_email: trevoke@gmail.com
author_url: http://trevoke.net
wordpress_id: 51
wordpress_url: http://trevoke.net/blog/?p=51
date: 2008-12-30 11:13:18.000000000 -05:00
categories:
- Uncategorized
tags:
- recursive
- vbs
- vbscript
comments: []
---
This is actually a lot simpler than I expected (gimme a break, this is my second foray into VBS!)

[sourcecode language='vb']Set fs = WScript.CreateObject ("Scripting.FileSystemObject")

Sub ShowSubFolders(Folder)
	For Each Subfolder In Folder.SubFolders
		Set files = SubFolder.Files
		For Each file In files
			WScript.Echo file.Name, file.Size
		Next
		ShowSubFolders Subfolder
	Next
End Sub

ShowSubFolders fs.GetFolder("C:\your\path\here")[/sourcecode]
