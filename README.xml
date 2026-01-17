<xml xmlns="http://www.w3.org/1999/xhtml" is_dbot="true" collection="false">
  <variables>
    <variable type="" id="j}8O`Vs+RJljIwPu-_:_" islocal="false" iscloud="false">Stake</variable>
    <variable type="" id="W4$:ZQCmEz#8+=4ysv5Y" islocal="false" iscloud="false">MaxLoss</variable>
    <variable type="" id="mXtFswo{p,|%W1:V-$+r" islocal="false" iscloud="false">TargetProfit</variable>
    <variable type="" id="%L?;380E6Lr^3b.%}t5Q" islocal="false" iscloud="false">BaseStake</variable>
    <variable type="" id=":[OEJdmz6Au]B;?D}85Q" islocal="false" iscloud="false">text</variable>
    <variable type="" id="fuQi3z)yh-[V/U%YTJ.2" islocal="false" iscloud="false">text1</variable>
    <variable type="" id="wBM,|Pk5nM15cpK5R3Kn" islocal="false" iscloud="false">text2</variable>
    <variable type="" id="9R]TXvv|/7gDPe[p-gDZ" islocal="false" iscloud="false">text3</variable>
    <variable type="" id="new_var_mart_level" islocal="false" iscloud="false">MartLevel</variable>
  </variables>
  <block type="trade_definition" id="=l`M:iIyHzz`#=5#|XK6" x="0" y="0">
    <statement name="TRADE_OPTIONS">
      <block type="trade_definition_market" id="gIVdlFG%DasAatr9N7WZ" deletable="false" movable="false">
        <field name="MARKET_LIST">synthetic_index</field>
        <field name="SUBMARKET_LIST">random_index</field>
        <field name="SYMBOL_LIST">R_100</field>
        <next>
          <block type="trade_definition_tradetype" id="cB2Gi-p|bT3-yd442,c{" deletable="false" movable="false">
            <field name="TRADETYPECAT_LIST">digits</field>
            <field name="TRADETYPE_LIST">overunder</field>
            <next>
              <block type="trade_definition_contracttype" id="Tyr;d8+6aiA0]6=|^+)K" deletable="false" movable="false">
                <field name="TYPE_LIST">both</field>
                <next>
                  <block type="trade_definition_candleinterval" id="-MbIlV6Mw#TR^XoJZRM+" deletable="false" movable="false">
                    <field name="CANDLEINTERVAL_LIST">60</field>
                    <next>
                      <block type="trade_definition_restartbuysell" id="`;!:ygyOsiO4Cfi*l^J~" deletable="false" movable="false">
                        <field name="TIME_MACHINE_ENABLED">FALSE</field>
                      </block>
                    </next>
                  </block>
                </next>
              </block>
            </next>
          </block>
        </next>
      </block>
    </statement>
    <statement name="INITIALIZATION">
      <block type="variables_set" id="init1">
        <field name="VAR" id="j}8O`Vs+RJljIwPu-_:_" variabletype="">Stake</field>
        <value name="VALUE">
          <block type="math_number"><field name="NUM">0.35</field></block>
        </value>
        <next>
          <block type="variables_set" id="init2">
            <field name="VAR" id="%L?;380E6Lr^3b.%}t5Q" variabletype="">BaseStake</field>
            <value name="VALUE">
              <block type="math_number"><field name="NUM">0.35</field></block>
            </value>
            <next>
              <block type="variables_set" id="init3">
                <field name="VAR" id="mXtFswo{p,|%W1:V-$+r" variabletype="">TargetProfit</field>
                <value name="VALUE">
                  <block type="math_number"><field name="NUM">100</field></block>
                </value>
                <next>
                  <block type="variables_set" id="init4">
                    <field name="VAR" id="W4$:ZQCmEz#8+=4ysv5Y" variabletype="">MaxLoss</field>
                    <value name="VALUE">
                      <block type="math_number"><field name="NUM">-150</field></block>
                    </value>
                    <next>
                      <block type="variables_set" id="init5">
                        <field name="VAR" id="new_var_mart_level" variabletype="">MartLevel</field>
                        <value name="VALUE">
                          <block type="math_number"><field name="NUM">0</field></block>
                        </value>
                      </block>
                    </next>
                  </block>
                </next>
              </block>
            </next>
          </block>
        </next>
      </block>
    </statement>
    <statement name="SUBMARKET">
      <block type="trade_definition_tradeoptions" id="-pji.8nn7cgY.tyQWt}a">
        <mutation has_first_barrier="false" has_second_barrier="false" has_prediction="true"></mutation>
        <field name="DURATIONTYPE_LIST">t</field>
        <value name="DURATION">
          <block type="math_number"><field name="NUM">1</field></block>
        </value>
        <value name="AMOUNT">
          <block type="variables_get">
            <field name="VAR" id="j}8O`Vs+RJljIwPu-_:_">Stake</field>
          </block>
        </value>
        <value name="PREDICTION">
          <block type="math_number"><field name="NUM">4</field></block>
        </value>
      </block>
    </statement>
  </block>

  <block type="before_purchase" id="before" x="0" y="600">
    <statement name="BEFOREPURCHASE_STACK">
      <block type="purchase" id="purchase">
        <field name="PURCHASE_LIST">DIGITOVER</field>
      </block>
    </statement>
  </block>

  <block type="after_purchase" id="after" x="0" y="800">
    <statement name="AFTERPURCHASE_STACK">
      <block type="controls_if" id="win_check">
        <mutation else="1"></mutation>
        <value name="IF0">
          <block type="contract_check_result">
            <field name="CHECK_RESULT">win</field>
          </block>
        </value>
        <statement name="DO0">
          <!-- Win: Reset stake & mart level -->
          <block type="variables_set">
            <field name="VAR" id="j}8O`Vs+RJljIwPu-_:_">Stake</field>
            <value name="VALUE">
              <block type="variables_get">
                <field name="VAR" id="%L?;380E6Lr^3b.%}t5Q">BaseStake</field>
              </block>
            </value>
            <next>
              <block type="variables_set">
                <field name="VAR" id="new_var_mart_level">MartLevel</field>
                <value name="VALUE">
                  <block type="math_number"><field name="NUM">0</field></block>
                </value>
              </block>
            </next>
          </block>
        </statement>
        <statement name="ELSE">
          <!-- Loss: Increase stake with martingale -->
          <block type="math_change" id="increase_stake">
            <field name="VAR" id="new_var_mart_level">MartLevel</field>
            <value name="DELTA">
              <block type="math_number"><field name="NUM">1</field></block>
            </value>
            <next>
              <block type="controls_if" id="mart_limit">
                <value name="IF0">
                  <block type="logic_compare">
                    <field name="OP">LTE</field>
                    <value name="A">
                      <block type="variables_get">
                        <field name="VAR" id="new_var_mart_level">MartLevel</field>
                      </block>
                    </value>
                    <value name="B">
                      <block type="math_number"><field name="NUM">4</field></block>
                    </value>
                  </block>
                </value>
                <statement name="DO0">
                  <block type="variables_set">
                    <field name="VAR" id="j}8O`Vs+RJljIwPu-_:_">Stake</field>
                    <value name="VALUE">
                      <block type="math_arithmetic">
                        <field name="OP">MULTIPLY</field>
                        <value name="A">
                          <block type="variables_get">
                            <field name="VAR" id="Stake">Stake</field>
                          </block>
                        </value>
                        <value name="B">
                          <block type="math_number"><field name="NUM">2.1</field></block>
                        </value>
                      </block>
                    </value>
                  </block>
                </statement>
                <statement name="ELSE">
                  <!-- Over limit: reset -->
                  <block type="variables_set">
                    <field name="VAR" id="j}8O`Vs+RJljIwPu-_:_">Stake</field>
                    <value name="VALUE">
                      <block type="variables_get">
                        <field name="VAR" id="%L?;380E6Lr^3b.%}t5Q">BaseStake</field>
                      </block>
                    </value>
                    <next>
                      <block type="variables_set">
                        <field name="VAR" id="new_var_mart_level">MartLevel</field>
                        <value name="VALUE">
                          <block type="math_number"><field name="NUM">0</field></block>
                        </value>
                      </block>
                    </next>
                  </block>
                </statement>
              </block>
            </next>
          </block>
        </statement>
        <next>
          <!-- Total profit check & notify -->
          <block type="controls_if" id="stop_profit">
            <mutation else="1"></mutation>
            <value name="IF0">
              <block type="logic_compare">
                <field name="OP">GTE</field>
                <value name="A">
                  <block type="total_profit"></block>
                </value>
                <value name="B">
                  <block type="variables_get">
                    <field name="VAR" id="mXtFswo{p,|%W1:V-$+r">TargetProfit</field>
                  </block>
                </value>
              </block>
            </value>
            <statement name="DO0">
              <block type="text_print">
                <value name="TEXT">
                  <block type="text_join">
                    <mutation items="2"></mutation>
                    <value name="0">
                      <block type="text"><field name="TEXT">🎉 Target Profit Hit! Total: </field></block>
                    </value>
                    <value name="1">
                      <block type="total_profit"></block>
                    </value>
                  </block>
                </value>
              </block>
            </statement>
            <statement name="ELSE">
              <block type="controls_if" id="stop_loss">
                <value name="IF0">
                  <block type="logic_compare">
                    <field name="OP">LTE</field>
                    <value name="A">
                      <block type="total_profit"></block>
                    </value>
                    <value name="B">
                      <block type="variables_get">
                        <field name="VAR" id="W4$:ZQCmEz#8+=4ysv5Y">MaxLoss</field>
                      </block>
                    </value>
                  </block>
                </value>
                <statement name="DO0">
                  <block type="text_print">
                    <value name="TEXT">
                      <block type="text_join">
                        <mutation items="2"></mutation>
                        <value name="0">
                          <block type="text"><field name="TEXT">❌ Stop Loss Hit! Total: </field></block>
                        </value>
                        <value name="1">
                          <block type="total_profit"></block>
                        </value>
                      </block>
                    </value>
                  </block>
                </statement>
                <next>
                  <block type="trade_again"></block>
                </next>
              </block>
            </statement>
          </block>
        </next>
      </block>
    </statement>
  </block>
</xml>
