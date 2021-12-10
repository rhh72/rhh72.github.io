<%@ Page Title="" Language="C#" CodeFile="NDALog.aspx.cs" Inherits="webpages_LSPM_Summary_Default" ValidateRequest = "false" EnableEventValidation="false" %>

<!DOCTYPE html>
<html>

<meta name="viewport" content="width=device-width, initial-scale=1.0"/> 
<meta name="viewport" content="target-densitydpi=device-dpi" /> 
<meta name="HandheldFriendly" content="true"/>
<link rel="stylesheet" href="../../js/stylev2.1.css">
    <link rel="stylesheet" href="../../js/fontawesome-pro-5.2.0-web/css/all.css">

            <head>    <link rel="icon" href="../../Images/LS Logo Box.jpg"><link rel="apple-touch-icon" href="https://media.licdn.com/mpr/mpr/shrink_200_200/AAEAAQAAAAAAAAW0AAAAJGQyZTBkOTIyLTYyMTEtNGQ5Yi05MjU1LTgyNzNjY2MwMTNlMQ.png">
                <META HTTP-EQUIV="REFRESH" CONTENT="43200;URL=../../.auth/logout">
            </head>
        <title>Shares To Notification</title> 
       <script src="jquery.min.js" type="text/javascript"></script>
    <script src="jquery-ui.min.js" type="text/javascript"></script>
        <link rel="stylesheet" href="jquery-ui.css">
<body>
   
<nav class="w3-sidenavMobile w3-collapse w3-blue w3-card-2" runat="server" id="mySidenav">
 <a href="#" onclick="w3_close()" class="w3-closenav w3-hide-large" style="border-bottom:1px solid black;">Close &times;</a> 
        <div id="SpotlightIconDiv" runat="server" class="desktopSpotlightIcon">
    <a href="../LSPM/LSPMSummary.aspx" style="padding:0;padding-top:4px;background-color:white;"><img src='../../Images/spotlightlogo.png' id="SpotlightPicture" runat="server" width="150"/></a>
        </div>
    <div class="divbanner" style="border-top:0px solid white;padding-top:5px">&nbsp;&nbsp;&nbsp;Portfolio</div>
    <a href="../LSPM/LSPMSummary.aspx"><i class="far fa-home fa-fw"></i> HF Port Mgmt</a>
    <a href="../LSPMLongOnly/LSPMSummary.aspx"><i class="far fa-chart-line fa-fw"></i> LO Port Mgmt</a> <a href="../LSPM/IPO_Home.aspx"><i class="fa fa-arrow-up"></i>&nbsp; IPO Port Mgmt</a> 
     <a href="../LSPMPrivate/PrivatePortfolio.aspx"><i class="far fa-handshake fa-fw"></i> Private Port Mgmt</a> 
    <a href="../Default.aspx"><i class="far fa-file-alt fa-fw"></i> Portfolio News</a>
    <div class="divbanner">&nbsp;&nbsp;&nbsp;Research</div>
    <a  href="../LSPM/LSPMScorecard.aspx"><i class="far fa-flag fa-fw"></i> Public Co. Mgmt</a> 
    <a href="../LSPM/IdeaPipeline.aspx"><i class="far fa-lightbulb fa-fw"></i> New Public Ideas</a>
     <a href="../LSPMPrivate/IdeaPipeline.aspx"><i class="far fa-lightbulb fa-fw"></i> New Private Ideas</a>
    <a href="../ResearchSupport/ResearchHome.aspx"><i class="far fa-search fa-fw"></i> Data Science</a> 
    <a href="../RMS/PersonHome.aspx"><i class="far fa-users fa-fw"></i> Relationships</a> 
    
    <div class="divbanner">&nbsp;&nbsp;&nbsp;Reports</div>
    <a href="../Analytics/RiskStatistics.aspx"><i class="far fa-calendar fa-fw"></i> HF Historical</a>   
    <a href="../Analytics/LORiskStatistics.aspx"><i class="far fa-calendar fa-fw"></i> LO Historical</a> 
    <a href="../Analytics/VaRAnalysis.aspx"><i class="far fa-chart-bar fa-fw"></i> Risk Analysis</a>
    <a class="w3-text-teal" href="../Ops/OpsReports.aspx"><i class="far fa-folder-open fa-fw"></i> Operations</a>
    <a href="../Information/BrokerContacts.aspx"><i class="far fa-money-bill-alt fa-fw"></i> Brokers</a>
    <div class="divbanner">&nbsp;&nbsp;&nbsp;Productivity</div>
    <a href="../Information/mySpotlight.aspx"><i class="far fa-user-circle fa-fw"></i> <%=System.Threading.Thread.CurrentThread.CurrentCulture.TextInfo.ToTitleCase(CurrentUser)%> <span class="numberCircle1"><%=ToDoCount%></span></a>
    <a href="../Information/CloudApplications.aspx"><i class="far fa-cloud fa-fw"></i> Cloud Apps</a><a href="../Ops/MSSecurityMaster.aspx"><i class="far fa-cog fa-fw"></i> Settings</a>
</nav>

<div class="w3-main" style="margin-left:160px; padding-bottom:100px;">
<header class="w3-container w3-light-blue">
  <span class="w3-opennav w3-xlarge w3-hide-large" style="float:left;padding-top:17px;padding-right:22px" onclick="w3_open()"><img src="../../Images/threelines.png" height="40" /></span>
  <div class="cls" runat="server" id="MyServerControlDiv" style="float:left"></div>
</header>
  

    <div class="w3-barMobile w3-orange" runat="server" id="OrangeNAVBar">
    <a class="w3-bar-item w3-button" href="OpsReports.aspx">Reports</a>
        <a class="w3-bar-item w3-button" href="../Ops/OpsAUMErin.aspx">AUM</a>   
        <a class="w3-bar-item w3-button" href="../Ops/FlowPipeline.aspx">Fundraising</a>    
        <a class="w3-bar-item w3-button" href="../Ops/Transparency.aspx">HF Transparency</a>   
        <a class="w3-bar-item w3-button" href="../Ops/LOTransparency.aspx">LO Transparency</a>    
    <a class="w3-bar-item w3-button" href="../LSPM/LSPMPTH.aspx">PTH</a>    
        <a class="w3-bar-item w3-button" href="../LSPM/LSPMDividend.aspx">Dividend</a>    
        <a class="w3-bar-item w3-button" href="../Ops/StockLoanComparison.aspx">Stock Loan</a>   
        <a class="w3-bar-item w3-button" href="../Ops/SharesToNotification.aspx">Notification</a>   
        <a class="w3-bar-item w3-button w3-text-white" href="../Ops/NDALog.aspx">NDA Log</a>  
        <a class="w3-bar-item w3-button" href="../Ops/RestrictedList.aspx">Restricted List</a>    
        <a class="w3-bar-item w3-button" href="../LSPM/LSPMTaxHarvesting.aspx">HF Tax Harvest</a> 
        <a class="w3-bar-item w3-button" href="../LSPMLongOnly/LSPMTaxHarvesting.aspx">LO Tax Harvest</a>     
        <a class="w3-bar-item w3-button" href="../Ops/HolidaySchedule.aspx">Holidays</a>   
</div>

   <form runat="server">
        <div class="w3-container">
            <iframe src="https://appbaseio-apps.github.io/booksearch/" height="600" width="800" />
          
    </div>
      </form>
    
<script>
    function w3_open() {
        document.getElementById("mySidenav").style.display = "block";
        
    }
    function w3_close() {
        document.getElementById("mySidenav").style.display = "none";
        
    }
    function myAccFunc() {
        var x = document.getElementById("demoAcc");
        if (x.className.indexOf("w3-show") == -1) {
            x.className += " w3-show";
            x.previousElementSibling.className += " w3-orange";
        } else {
            x.className = x.className.replace(" w3-show", "");
            x.previousElementSibling.className =
            x.previousElementSibling.className.replace(" w3-orange", "");
        }
    }
    function myAccFunc2() {
        var x = document.getElementById("demoAcc2");
        if (x.className.indexOf("w3-show") == -1) {
            x.className += " w3-show";
            x.previousElementSibling.className += " w3-black";
        } else {
            x.className = x.className.replace(" w3-show", "");
            x.previousElementSibling.className =
            x.previousElementSibling.className.replace(" w3-black", "");
        }
    }

</script>
     
</body>
</html>
