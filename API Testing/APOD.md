##API Testing of the NASA the Astronomy Picture of the Day section with Postman.

###Pre-conditions:
####Open https://api.nasa.gov/, 
####Sign up https://api.nasa.gov/#signUp,
####Get an api key.

###Query Parameters
![Parameters](https://drive.google.com/drive/folders/1sWB-bOjcuz_xS2CdF-kb7y0oD0SLG9k8)
###Description of Request Parameters:
###**date** The date of the APOD image. Defaults to today's date. 1995-06-16 is the first day an APOD picture was posted, so date can't be less than that day. Also date can't be more than the current date. 
###**start_date** The date indicating the start of a date range. Can't be used with date.
###**end_date** The date indicating the end of a date range. Can't be used with date.  If start_date is specified without an end_date then end_date defaults to the current date.
###**thrumbs** A boolean parameter inidcating whether the API should return a thumbnail image URL for video files. If set to True, the API returns URL of video thumbnail. If an APOD is not a video, this parameter is ignored.
###**count** A positive integer, no more than 100. If this is specified then count randomly chosen images will be returned in a JSON array.

###Example query:
###https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY
________

##Positive checks:

###:small_blue_diamond:Date: 
https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY&date=2021-10-14
###See Return Object :arrow_down_small:
```JSON
{
    "copyright": "Ignacio Diaz Bobillo",
    "date": "2021-10-14",
    "explanation": "A mere seven hundred light years from Earth, toward the constellation Aquarius, a sun-like star is dying. Its last few thousand years have produced the Helix Nebula (NGC 7293), a well studied and nearby example of a Planetary Nebula, typical of this final phase of stellar evolution.  A total of 90 hours of exposure time have gone in to creating this expansive view of the nebula. Combining narrow band image data from emission lines of hydrogen atoms in red and oxygen atoms in blue-green hues, it shows remarkable details of the Helix's brighter inner region about 3 light-years across. The white dot at the Helix's center is this Planetary Nebula's hot, central star. A simple looking nebula at first glance, the Helix is now understood to have a surprisingly complex geometry.",
    "hdurl": "https://apod.nasa.gov/apod/image/2110/Helix_Oxygen_crop2.jpg",
    "media_type": "image",
    "service_version": "v1",
    "title": "NGC 7293: The Helix Nebula",
    "url": "https://apod.nasa.gov/apod/image/2110/Helix_Oxygen_crop2_1024.jpg"
}
```
###:small_blue_diamond:End_date:
https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY&end_date
###See Return Object :arrow_down_small:
```JSON
{
    "copyright": "Ignacio Diaz Bobillo",
    "date": "2021-10-14",
    "explanation": "A mere seven hundred light years from Earth, toward the constellation Aquarius, a sun-like star is dying. Its last few thousand years have produced the Helix Nebula (NGC 7293), a well studied and nearby example of a Planetary Nebula, typical of this final phase of stellar evolution.  A total of 90 hours of exposure time have gone in to creating this expansive view of the nebula. Combining narrow band image data from emission lines of hydrogen atoms in red and oxygen atoms in blue-green hues, it shows remarkable details of the Helix's brighter inner region about 3 light-years across. The white dot at the Helix's center is this Planetary Nebula's hot, central star. A simple looking nebula at first glance, the Helix is now understood to have a surprisingly complex geometry.",
    "hdurl": "https://apod.nasa.gov/apod/image/2110/Helix_Oxygen_crop2.jpg",
    "media_type": "image",
    "service_version": "v1",
    "title": "NGC 7293: The Helix Nebula",
    "url": "https://apod.nasa.gov/apod/image/2110/Helix_Oxygen_crop2_1024.jpg"
}
```
###:small_blue_diamond:First_date:
https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY&date=1995-06-16
###See Return Object :arrow_down_small:
```JSON
{
    "date": "1995-06-16",
    "explanation": "Today's Picture:    Explanation:  If the Earth could somehow be transformed to the ultra-high density of a neutron star , it might appear as it does in the above computer generated figure. Due to the very strong gravitational field, the neutron star distorts light from the background sky greatly. If you look closely, two images of the constellation Orion are visible. The gravity of this particular neutron star is so great that no part of the neutron star is blocked from view - light is pulled around by gravity even from the back of the neutron star.   We keep an  archive file.  Astronomy Picture of the Day is brought to you by  Robert Nemiroff and  Jerry Bonnell . Original material on this page is copyrighted to Robert Nemiroff and Jerry Bonnell.",
    "hdurl": "https://apod.nasa.gov/apod/image/e_lens.gif",
    "media_type": "image",
    "service_version": "v1",
    "title": "Neutron Star Earth",
    "url": "https://apod.nasa.gov/apod/image/e_lens.gif"
}
```
###:small_blue_diamond:Start_date:
https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY&start_date
###See Return Object :arrow_down_small:
```JSON
{
    "copyright": "Ignacio Diaz Bobillo",
    "date": "2021-10-14",
    "explanation": "A mere seven hundred light years from Earth, toward the constellation Aquarius, a sun-like star is dying. Its last few thousand years have produced the Helix Nebula (NGC 7293), a well studied and nearby example of a Planetary Nebula, typical of this final phase of stellar evolution.  A total of 90 hours of exposure time have gone in to creating this expansive view of the nebula. Combining narrow band image data from emission lines of hydrogen atoms in red and oxygen atoms in blue-green hues, it shows remarkable details of the Helix's brighter inner region about 3 light-years across. The white dot at the Helix's center is this Planetary Nebula's hot, central star. A simple looking nebula at first glance, the Helix is now understood to have a surprisingly complex geometry.",
    "hdurl": "https://apod.nasa.gov/apod/image/2110/Helix_Oxygen_crop2.jpg",
    "media_type": "image",
    "service_version": "v1",
    "title": "NGC 7293: The Helix Nebula",
    "url": "https://apod.nasa.gov/apod/image/2110/Helix_Oxygen_crop2_1024.jpg"
}
```
###:small_blue_diamond:Date_range:
https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY&start_date=2021-10-11&end_date=2021-10-13
###See Return Object :arrow_down_small:
```JSON
[
    {
        "date": "2021-10-11",
        "explanation": "What would it be like to fly over the largest moon in the Solar System? In June, the robotic Juno spacecraft flew past Jupiter's huge moon Ganymede and took images that have been digitally constructed into a detailed flyby. As the featured video begins, Juno swoops over the two-toned surface of the 2,000-km wide moon, revealing an icy alien landscape filled with grooves and craters. The grooves are likely caused by shifting surface plates, while the craters are caused by violent impacts. Continuing on in its orbit, Juno then performed its 34th close pass over Jupiter's clouds. The digitally-constructed video shows numerous swirling clouds in the north, colorful planet-circling zones and bands across the middle -- featuring several white-oval clouds from the String of Pearls, and finally more swirling clouds in the south.  Next September, Juno is scheduled to make a close pass over another of Jupiter's large moons: Europa.",
        "media_type": "video",
        "service_version": "v1",
        "title": "Juno Flyby of Ganymede and Jupiter",
        "url": "https://www.youtube.com/embed/CC7OJ7gFLvE?rel=0"
    },
    {
        "copyright": "Hao Qin",
        "date": "2021-10-12",
        "explanation": "What makes a meteor a fireball?  First of all, everyone agrees that a fireball is an exceptionally bright meteor. Past that, the International Astronomical Union defines a fireball as a meteor brighter than apparent magnitude -4, which corresponds (roughly) to being brighter than any planet -- as well as bright enough to cast a human-noticeable shadow.  Pictured, an astrophotographer taking a long-duration sky image captured by accident the brightest meteor he had ever seen.  Clearly a fireball, the disintegrating space-rock created a trail so bright it turned night into day for about two seconds earlier this month.  The fireball has been artificially dimmed in the featured image to bring up foreground Lake Louise in Alberta, Canada.  Although fireballs are rare, many people have been lucky enough to see them.  If you see a fireball, you can report it.  If more than one person recorded an image, the fireball might be traceable back to the Solar System body from which it was ejected.",
        "hdurl": "https://apod.nasa.gov/apod/image/2110/FireballAlberta_Qin_5568.jpg",
        "media_type": "image",
        "service_version": "v1",
        "title": "Fireball over Lake Louise",
        "url": "https://apod.nasa.gov/apod/image/2110/FireballAlberta_Qin_1080.jpg"
    },
    {
        "copyright": "Yizhou Zhang",
        "date": "2021-10-13",
        "explanation": "It may look like a huge cosmic question mark, but the big question really is  how does the bright gas and dark dust tell this nebula's history of star formation.  At the edge of a giant molecular cloud toward the northern constellation Cepheus, the glowing star forming region NGC 7822 lies about 3,000 light-years away. Within the nebula, bright edges and dark shapes stand out in this colorful and detailed skyscape. The 9-panel mosaic, taken over 28 nights with a small telescope in Texas, includes data from narrowband filters, mapping emission from atomic oxygen, hydrogen, and sulfur into blue, green, and red hues. The emission line and color combination has become well-known as the Hubble palette. The atomic emission is powered by energetic radiation from the central hot stars. Their powerful winds and radiation sculpt and erode the denser pillar shapes and clear out a characteristic cavity light-years across the center of the natal cloud. Stars could still be forming inside the pillars by gravitational collapse but as the pillars are eroded away, any forming stars will ultimately be cut off from their reservoir of star stuff. This field of view spans over 40 light-years across at the estimated distance of NGC 7822.",
        "hdurl": "https://apod.nasa.gov/apod/image/2110/NGC7822_Yizhou_4044.jpg",
        "media_type": "image",
        "service_version": "v1",
        "title": "NGC 7822: Cosmic Question Mark",
        "url": "https://apod.nasa.gov/apod/image/2110/NGC7822_Yizhou_960.jpg"
    }
]
```
###:small_blue_diamond:Thumbs=true:
https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY&thumbs=true
###See Return Object :arrow_down_small:
```JSON
{
    "copyright": "Ignacio Diaz Bobillo",
    "date": "2021-10-14",
    "explanation": "A mere seven hundred light years from Earth, toward the constellation Aquarius, a sun-like star is dying. Its last few thousand years have produced the Helix Nebula (NGC 7293), a well studied and nearby example of a Planetary Nebula, typical of this final phase of stellar evolution.  A total of 90 hours of exposure time have gone in to creating this expansive view of the nebula. Combining narrow band image data from emission lines of hydrogen atoms in red and oxygen atoms in blue-green hues, it shows remarkable details of the Helix's brighter inner region about 3 light-years across. The white dot at the Helix's center is this Planetary Nebula's hot, central star. A simple looking nebula at first glance, the Helix is now understood to have a surprisingly complex geometry.",
    "hdurl": "https://apod.nasa.gov/apod/image/2110/Helix_Oxygen_crop2.jpg",
    "media_type": "image",
    "service_version": "v1",
    "title": "NGC 7293: The Helix Nebula",
    "url": "https://apod.nasa.gov/apod/image/2110/Helix_Oxygen_crop2_1024.jpg"
}
```
###:small_blue_diamond:Thumbs=false:
https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY&thumbs=false
###See Return Object :arrow_down_small:
```JSON
{
    "copyright": "Ignacio Diaz Bobillo",
    "date": "2021-10-14",
    "explanation": "A mere seven hundred light years from Earth, toward the constellation Aquarius, a sun-like star is dying. Its last few thousand years have produced the Helix Nebula (NGC 7293), a well studied and nearby example of a Planetary Nebula, typical of this final phase of stellar evolution.  A total of 90 hours of exposure time have gone in to creating this expansive view of the nebula. Combining narrow band image data from emission lines of hydrogen atoms in red and oxygen atoms in blue-green hues, it shows remarkable details of the Helix's brighter inner region about 3 light-years across. The white dot at the Helix's center is this Planetary Nebula's hot, central star. A simple looking nebula at first glance, the Helix is now understood to have a surprisingly complex geometry.",
    "hdurl": "https://apod.nasa.gov/apod/image/2110/Helix_Oxygen_crop2.jpg",
    "media_type": "image",
    "service_version": "v1",
    "title": "NGC 7293: The Helix Nebula",
    "url": "https://apod.nasa.gov/apod/image/2110/Helix_Oxygen_crop2_1024.jpg"
}
```
###:small_blue_diamond:Count=3:
https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY&count=3
###See Return Object :arrow_down_small:
```JSON
[
    {
        "copyright": "Phillip L. JonesVisualUniverse.org",
        "date": "2008-12-09",
        "explanation": "Perhaps the most famous star cluster on the sky, the Pleiades can be seen without binoculars from even the depths of a light-polluted city.  Also known as the Seven Sisters and M45, the Pleiades is one of the brightest and closest open clusters.   The Pleiades contains over 3,000 stars, is about 400 light years away, and only 13 light years across.  A prominent telescope and car company has borrowed the star cluster's name. Quite evident in the above photograph are the blue reflection nebulae that surround the brighter cluster stars.  Low mass, faint, brown dwarfs have also been found in the Pleiades.   digg_url = 'http://apod.nasa.gov/apod/ap081209.html'; digg_skin = 'compact';",
        "hdurl": "https://apod.nasa.gov/apod/image/0812/pleiades_jones_big.jpg",
        "media_type": "image",
        "service_version": "v1",
        "title": "M45: The Pleiades Star Cluster",
        "url": "https://apod.nasa.gov/apod/image/0812/pleiades_jones.jpg"
    },
    {
        "date": "2000-02-23",
        "explanation": "Our Sun's surface is continually changing.  This time-lapse movie shows in five seconds what happens in 20 minutes on the Sun's surface near a sunspot.  Visible is boiling granulation outside the sunspot, inward motion of bright grains in the outer penumbral region toward the sunspot, and the churning of small magnetic elements between  solar granules.  Sunspots themselves are relatively cool regions of the solar surface depressed by magnetic fields. The dark lanes surrounding the sunspot are called penumbral filaments, and recent computer simulations have shown that their behavior is also dominated by magnetic fields.  The above sequence was taken with the new Dutch Open Telescope last September and focused on a sunspot that measured about 25,000 kilometers across.",
        "hdurl": "https://apod.nasa.gov/apod/image/0002/sunspot_ps_big.gif",
        "media_type": "image",
        "service_version": "v1",
        "title": "Sunspot Seething",
        "url": "https://apod.nasa.gov/apod/image/0002/sunspot_ps.gif"
    },
    {
        "date": "2004-09-14",
        "explanation": "A flying saucer from outer space crash-landed in the Utah desert last week after being tracked by radar and chased by helicopters.  No space aliens were involved, however.  The saucer, pictured above, was the Genesis sample return capsule, part of a human-made robot Genesis spaceship launched three years ago by NASA itself to study the Sun.  The unexpectedly hard landing at over 300 kilometers per hour occurred because the parachutes did not open as planned.  The Genesis mission had been orbiting the Sun collecting solar wind particles that are usually deflected away by Earth's magnetic field.  A big question remains -- are the returned samples in good enough condition to recover information about the real composition of the Sun?  Genesis team scientists and engineers are working hard to find out.",
        "hdurl": "https://apod.nasa.gov/apod/image/0409/landing1_genesis_big.jpg",
        "media_type": "image",
        "service_version": "v1",
        "title": "Genesis Mission's Hard Impact",
        "url": "https://apod.nasa.gov/apod/image/0409/landing1_genesis.jpg"
    }
]
```

##Negative checks:

###:small_blue_diamond:First_date-1:
https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY&date=1995-06-15
See Return Object :arrow_down_small:
```JSON
{
    "code": 400,
    "msg": "Date must be between Jun 16, 1995 and Oct 14, 2021.",
    "service_version": "v1"
}
```
###:small_blue_diamond:End_date+1:
https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY&date=2021-10-15
See Return Object :arrow_down_small:
```JSON
{
    "code": 400,
    "msg": "Date must be between Jun 16, 1995 and Oct 14, 2021.",
    "service_version": "v1"
}
```
###:small_blue_diamond:Count=101:
https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY&count=101
See Return Object :arrow_down_small:
```JSON
{
    "code": 400,
    "msg": "Count must be positive and cannot exceed 100",
    "service_version": "v1"
}
```
###:small_blue_diamond:Count=-1:
https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY&count=-1
See Return Object :arrow_down_small:
```JSON
{
    "code": 400,
    "msg": "Count must be positive and cannot exceed 100",
    "service_version": "v1"
}
```





