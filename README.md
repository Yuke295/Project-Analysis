# COVID-19 Risk to Washington Workers Smart Dashboard Analysis

By [Yuke Cao](https://www.linkedin.com/in/yuke-cao-261838191/)

Link to hosted website: [COVID-19 Risk to Washington Workers Smart Dashboard](https://hgis.uw.edu/covid19-workers/)

## Project Description
![cover](img/cover.png)

### Goals

This is a Washington State COVID-19 Risk Assessment Dashboard, which includes COVID-risk, unemployment and occupational risk factors to assess local COVID-risk and unemployment levels. It is established to enable local governments, communities and workplaces to develop locally appropriate health and economic protection policies for workers during economic recovery; In order for Washington's communities to thrive in the wake of the COVID-19 pandemic and the associated socio-economic uncertainties, both public health and economic issues need to be addressed.

### Authors

![hgis](img/hgis.png)

This dashboard is made by [Bo Zhao](https://github.com/jakobzhao), a geography professor at the University of Washington and the Principal Investigator at [Humanistic GIS Laboratory](https://hgis.uw.edu/), with other members in HGIS Lab: Marissa Baker, Kim England, Ellie Cleasby, Fengyu Xu, Jou Ho, Xiaoqi Bao, Kyle Roland, Yuke Cao in 2020. This project is funded by the Population Health Initiative at University of Washington (UW), School of Public Health, Department of Geography and the Harry Bridges Center for Labor Studies; Hosted upon the server offered by UW's Center for Studies in Demography and Ecology (CSDE); Maintained by the UW's Humanistic GIS Laboratory. For more details about this project, visit the website of smart dashboard [COVID-19 Risk to Washington Workers](https://hgis.uw.edu/covid19-workers).

### Functions

The following are the main functionalities of this smart dashboard.
- A clickable map that allows user to navigate through different counties' risk in Washington State. The map contains four different features in different colors to estimate the overall risk level to workers is based on a holistic interpretation of the infection risk, unemployment risk and occupation risk.
- A zoom bar that allows users to zoom to the original map.
- The color scale to shows the risk level.
- A word could that be generated from the recent Twitter posts which contains 'covid' as a keyword.
- Each county has six graphics to show the different risk information.
  - The COVID-19 Infection Trend is shown as time-series graph. It has the aggregate infected COVID-19 confirmed cases, the aggregate deaths caused by the COVID-19, the number of patients who have been hospitalized and the incidence rate.
  - The Average unemployment Rate and Average Unemployment Insurance Benefit (UIB) Per Claimant also changed by clicking different counties. The data is also represented by dot plot.
  - The Top Ten Counties with Highest Unemployment Rate is listed by bar graph.
  - The Occupations with Highest Employment are listed on next to Occupation Risk Matrix which is shown as scatterplot.
- A methodology page that contains the brief explanation of the methods they use to design this dashboard.
- A resource page that lists all the sources.
- An about page that has the overall information of the dashboard.

### Data Sources

- Sources
  - Labor Force by County Snapshot
  - Unemployment Insurance Claims and Benefits
  - O*NET data arranged by Exposure to disease/infection at work
  - O*NET data arranged by Works in physical proximity at work
  - Coronavirus Outbreak
  - ACS Data

- External Tools and Libraries
  - Bootstrap
  - leaflet
  - c3
  - d3
  - simplebar
  - easy-button
  - font-awesome
  - jQuery
  - rbush
  - labelgun
  - topojson
  - tweepy
  - nltk, VADER
  - wordcloud

## Systematic architecture
The smart dashboard is a very intuitive method of data visualization. A dashboard can present different data boards according to requirements. The main function of this project is to map the risk of COVID-19 infection among workers in Washington State by displaying different data. When a user clicks on a different county, the corresponding data changes. The front page of this dashboard is mainly divided into three parts. The header of the dashboard can be used to switch between different pages, including some sharing links for readers to share. The plate on the left mainly contains the basic introduction of this project and the module map for clicking to switch different counties. The panel on the right shows all the data visualization.

The following code is the part of the source code of `left-panel`:

  <div class="ct-grid-container grid-container">
    <div data-simplebar data-simplebar-auto-hide="true" class="grid-box">
      <div class="left-panel">
        <p id="county-name"></p>

        <div class="intro">
        </div>
        <div class="map-selector-group-1 btn-group-toggle">
          <label class="btn btn-secondary" id="overall">
            <input type="radio" name="options" autocomplete="off">
            Overall Risk Level to Workers
          </label>
        </div>
        <p><span class="overall-risk">High</span></p>
        <div class="map-selector-group-2 btn-group btn-group-sm btn-group-toggle" data-toggle="buttons">
        </div>
        <div id="map-container"></div>
        <div class="legend">
        </div>
        <hr>
        <div id="wcloud-title"> Online Discussion
          <i class="fa fa-info-circle tooltip" aria-hidden="true">
            <span class="tooltiptext"></span>
          </i>
          <span id="stackedBar-title" class="tooltip text-right">Sentiment Score
          </span>
        </div>
        <div>
          <img id="wcloud-img" src="assets/smedia/img/latest/adams.png" alt="wcloud">
        </div>
        <div class="logo"><a href="https://uw.edu" target="_blank"><img src="assets/imgs/uw.png" width="250px"></a></div>
      </div>
    </div>


I am the person who mainten and update this website. The data basically needs to be updated every half a month. We mainly use the Python documents we have already written to fetch the information we need from different websites and put it into our data documents for data updates. Later, we will also consider writing a model that automatically grabs the data to carry out real-time updates to the data, which will be much more convenient.

## The Critique of Overall UI/UX
Overall, the design of the dashboard is very reasonable. Dashboard is divided into sections to present specific information. When people click on the map on the left, the data on the right changes accordingly. This mode allows users to easily browse information from different regions. I think the color selection of the dashboard is also user-friendly. The background of the dashboard is dark, but it does not give people a negative feeling.  Instead, it highlights different features.The choice of color for data presentation is also reasonable, such as red or dark colors for high-risk areas.The rest of the colors are also presented with three primary colors.

One drawback, I think, is that Dashboard doesn't automatically reorder the sections based on the size of the screen when reducing the size of the site. Instead, user can swipe left and right on top of the original to see the complete plate. Personally, I think it would be better for the panel on the right, when the user switches to a smaller screen, to reorder everything according to the size of the screen and support scrolling up and down so that each module can be directly displayed within the corresponding size.

## Reflection
The idea of designing a dashboard to assess the risk of infection among workers in Washington State during the epidemic was a great one, and I am really happy to be involved in the project to learn. This idea is very useful for us since we are in the epidemic. The government or some relevant institutions can obtain useful data according to our dashboard to subsidize workers to different degrees or change corresponding policies to reduce the risk of infection of workers, so as to achieve better epidemic prevention and control work. Another thing I think is good about this dashboard is that it has a lot of information for us to understand the whole project.Compared with other dashboards that only have charts, it is more intuitive to let users know how to use it and other relevant information.

Dashboards are a great way to present data, but they have some drawbacks. Through studying and reading different articles in this class, I learned that The dashboard has "The Importance Trap".  The data on each dashboard is prioritized, and the IT people decide on the data prioritization, which means the dashboard design is somewhat subjective. It is easy for IT people to design dashboards that are not useful if they do not have a deep understanding of the needs of the company. So when we design our own dashboard, we need to understand what our own needs or the needs of our customers are, so that we can put the key information on the dashboard. The dashboards I mentioned above are subjective because when people design dashboards, it is usually based on the designer's ideas. The designer puts different data on the dashboard to show what he wants others to see. Therefore, when we are the users of the dashboard, we need to have some judgment and not blindly trust everything on the dashboard. This is the another trap we might face, "The context Trap". For the designers of dashboards, they need to be more objective in delivering useful metrics. The last thing he talked about is "The Causality Trap". The idea here is that when people look at the statistic report, it's easy to misinterpret cause and effect. I think, as a dashboard designer, you can add on some specific statements in the dashboard to make the point that you are presenting if necessary. For the user, it is necessary to consider some special cases to rule out erroneous conclusions.([3 Ways Data Dashboards Can Mislead You](https://hbr.org/2017/01/3-ways-data-dashboards-can-mislead-you#comment-section))

Personally, I think making dashboards is a very intuitive and effective way to visualize data. But when we are designing, we want to present the most useful information, and we need to add specific explanations to help users understand our dashboard. When we use someone else's dashboard, we also need to analyze and use the data in a rational way.
