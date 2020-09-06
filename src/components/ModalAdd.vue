<template>
    <div>
<b-modal id="addProduct" centered title="Add Item">
    <b-row>
        <b-col lg="12">
            <b-row class="my-3">
                <b-col lg="3">Name</b-col>
                <b-col lg="9">
                    <b-form-input></b-form-input>
                </b-col>
            </b-row>
            <b-row class="my-3">
                <b-col lg="3">Image</b-col>
                <b-col lg="9">
                    <b-form-file></b-form-file>
                </b-col>
            </b-row>
            <b-row class="my-3">
                <b-col lg="3">Price</b-col>
                <b-col lg="9">
                    <b-form-input></b-form-input>
                </b-col>
            </b-row>
            <b-row class="my-3">
                <b-col lg="3">Category</b-col>
                <b-col lg="9">
                    <div>
                        <b-input-group>
                            <b-form-input></b-form-input>

                            <template v-slot:append>
                            <b-dropdown text="Dropdown" variant="success">
                                <b-dropdown-item>Foods</b-dropdown-item>
                                <b-dropdown-item>Beverages</b-dropdown-item>
                            </b-dropdown>
                            </template>
                        </b-input-group>
                        </div>
                </b-col>
            </b-row>
        </b-col>
    </b-row>
  </b-modal>
</div>

</template>
