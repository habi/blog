---
author: admin
categories:
- apple
- technospeak
comments: true
date: 2004-10-29T19:57:12Z
link: http://habi.gna.ch/2004/10/29/address-book-apple-script/
slug: address-book-apple-script
title: address book apple-script
url: /2004/10/29/address-book-apple-script/
wordpress_id: 663
---

the [powerbook blog](http://powerbook.blogger.de/stories/167895/) linked to a nice hint on [macosxhints.ch](http://www.macosxhints.ch/index.php?page=2&hintid=1163) (features german translations of [osxhints.com](http://www.macosxhints.com/), but also original german hints).
you might have seen that you can click on any label in a contacts detail (e.g. work address, telephone, etc) to get a nice menu to do things with the data (get it in huge letters all over your screen, look for the map, print label, etc.).
since the release of panther coders can add to these menus with little apple-script-effort. the script mentioned in the hints adds an european map search, but i wanted to alter it to use the excellent [map.search.ch](http://map.search.ch/). after downloading the nice applescript i changed it to this point:



<blockquote>using terms from application "Address Book"  

	on action property  

		return "address"  

	end action property  
  

	
	on action title for thePerson with theAddress  

		return "mit map.search.ch anzeigen"  

	end action title  
  

	
	on should enable action for thePerson with theAddress  

		return true  

	end should enable action  
  

	
	on perform action for thePerson with theAddress  

		tell application "Address Book"  

			set z to zip of theAddress  

			set c to city of theAddress  

			set s to street of theAddress  

		end tell  

		tell application "Safari"  

			set browser to make new document  

			tell browser  

				set URL to "http://map.search.ch/" & z & "-" & c & "/" & s  

			end tell  

		end tell  

		return true  

	end perform action  

end using terms from</blockquote>



so, to use the script, just open script editor, paste the code above (or FAR better, just [click here](//com.apple.scripteditor/?action=new&script=using%20terms%20from%20application%20%22Address%20Book%22%0A%09on%20action%20property%09%0A%09return%20%22address%22%0A%09end%20action%20property%09%0A%09on%20action%20title%20for%20thePerson%20with%20theAddress%09%0A%09return%20%22mit%20map.search.ch%20anzeigen%22%0A%09end%20action%20title%09%0A%09on%20should%20enable%20action%20for%20thePerson%20with%20theAddress%09%0A%09return%20true%0A%09end%20should%20enable%20action%09%0A%09on%20perform%20action%20for%20thePerson%20with%20theAddress%09%0A%09tell%20application%20%22Address%20Book%22%09%09%0A%09set%20z%20to%20zip%20of%20theAddress%09%09%0A%09set%20c%20to%20city%20of%20theAddress%09%09%0A%09set%20s%20to%20street%20of%20theAddress%09%0A%09end%20tell%09%0A%09tell%20application%20%22Safari%22%09%09%0A%09set%20browser%20to%20make%20new%20document%09%09%0A%09tell%20browser%09%09%09%0A%09set%20URL%20to%20%22http://map.search.ch/%22%20&%20z%20&%20%22-%22%20&%20c%20&%20%22/%22%20&%20s%09%09%0A%09end%20tell%09%0A%09end%20tell%09%0A%09return%20true%0A%09end%20perform%20action%0A%20end%20using%20terms%20from)1), save as "script" in ~/Library/Address Book Plug-Ins/ restart your address book and have fun with the address label.
it should work with all swiss addresses, if it doesn't send me a note and i'll try to fix it... 
**oh, and i forgot to mention**: the whole thing only works for os x.3!

1that link took me ages!
