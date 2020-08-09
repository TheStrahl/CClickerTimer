function time_convert(num)
	{ 
	var hours = Math.floor(num / 60);  
	var minutes = num % 60;
	return hours + ":" + minutes;         
	}

Game.Win=function(what)
	{
	if (typeof what==='string')
		{
		if (Game.Achievements[what])
			{
			if (Game.Achievements[what].won==0)
				{
				var name=Game.Achievements[what].shortName?Game.Achievements[what].shortName:Game.Achievements[what].name;
				Game.Achievements[what].won=1;
				if (Game.prefs.popups) Game.Popup('Achievement unlocked :<br>'+name);
				else Game.Notify('Earned in ' + time_convert(((Date.now()-Game.fullDate)/1000).toFixed(2)),'<div class="title" style="font-size:18px;margin-top:-2px;">'+name+'</div>',Game.Achievements[what].icon);
				if (Game.CountsAsAchievementOwned(Game.Achievements[what].pool)) Game.AchievementsOwned++;
				Game.recalculateGains=1;
				}
			}
		}
	else {for (var i in what) {Game.Win(what[i]);}}
	}
