# log4net.multiprocess
add multiple process rolling file appender support

rolling size should set staticlogfilename to false

log4net config:
<code>
  <log4net>
    <root>
      <level value="ERROR"/>
      <appender-ref ref="RollingFileAppender"/>
    </root>
    <appender name="RollingFileAppender" type="log4net.Appender.MultipleProcessRollingFileAppender">
      <file value="Log\system.log"/>
      <lockingModel type="log4net.Appender.MultipleProcessRollingFileAppender+InterProcessLock"/>
      <datePattern value="(yyyyMMdd)"/>
      <appendToFile value="true"/>
      <RollingStyle value="Size"/>
      <staticLogFileName value="false"/>
      <MaxSizeRollBackups value="-1"/>
      <maximumFileSize value="500KB"/>
      <layout type="log4net.Layout.PatternLayout">
        <conversionPattern value="%date [%t]%-5p %c - %m%n"/>
      </layout>
    </appender>
  </log4net>
</code>
